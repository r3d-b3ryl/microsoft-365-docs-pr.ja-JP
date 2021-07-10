---
title: macOS のデバイスコントロール
description: Usb デバイスなどのリムーバブル 記憶域からの脅威を軽減するために Microsoft Defender for Endpoint on Mac を構成する方法について説明します。
keywords: microsoft, defender, Microsoft Defender for Endpoint, mac, device, control, usb, リムーバブル, メディア
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: security
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
ms.openlocfilehash: 5cb819daa11a50ef54c758a6aa696a5fc645029c
ms.sourcegitcommit: 7dc3b4dec05299abb4290a6e3d1ebe0fdc622ed7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2021
ms.locfileid: "53363981"
---
# <a name="device-control-for-macos"></a><span data-ttu-id="092b4-104">macOS のデバイスコントロール</span><span class="sxs-lookup"><span data-stu-id="092b4-104">Device control for macOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="092b4-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="092b4-105">**Applies to:**</span></span>
- [<span data-ttu-id="092b4-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="092b4-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="092b4-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="092b4-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="092b4-108">Microsoft Defender ATP を試してみたいですか?</span><span class="sxs-lookup"><span data-stu-id="092b4-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="092b4-109">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="092b4-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

## <a name="requirements"></a><span data-ttu-id="092b4-110">Requirements</span><span class="sxs-lookup"><span data-stu-id="092b4-110">Requirements</span></span>

<span data-ttu-id="092b4-111">macOS のデバイスコントロールには、次の前提条件があります。</span><span class="sxs-lookup"><span data-stu-id="092b4-111">Device control for macOS has the following prerequisites:</span></span>

>[!div class="checklist"]
> - <span data-ttu-id="092b4-112">Microsoft Defender for Endpoint の資格 (試用版の場合があります)</span><span class="sxs-lookup"><span data-stu-id="092b4-112">Microsoft Defender for Endpoint entitlement (can be trial)</span></span>
> - <span data-ttu-id="092b4-113">最小 OS バージョン: macOS 11 以上</span><span class="sxs-lookup"><span data-stu-id="092b4-113">Minimum OS version: macOS 11 or higher</span></span>
> - <span data-ttu-id="092b4-114">最小製品バージョン: 101.34.20</span><span class="sxs-lookup"><span data-stu-id="092b4-114">Minimum product version: 101.34.20</span></span>

## <a name="device-control-policy"></a><span data-ttu-id="092b4-115">デバイス制御ポリシー</span><span class="sxs-lookup"><span data-stu-id="092b4-115">Device control policy</span></span>

<span data-ttu-id="092b4-116">macOS のデバイスコントロールを構成するには、組織内で設定する制限を説明するポリシーを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="092b4-116">To configure device control for macOS, you must create a policy that describes the restrictions you want to put in place within your organization.</span></span>

<span data-ttu-id="092b4-117">デバイス制御ポリシーは、他のすべての製品設定を構成するために使用される構成プロファイルに含まれています。</span><span class="sxs-lookup"><span data-stu-id="092b4-117">The device control policy is included in the configuration profile used to configure all other product settings.</span></span> <span data-ttu-id="092b4-118">詳細については、「構成プロファイル [構造」を参照してください](mac-preferences.md#configuration-profile-structure)。</span><span class="sxs-lookup"><span data-stu-id="092b4-118">For more information, see [Configuration profile structure](mac-preferences.md#configuration-profile-structure).</span></span>

<span data-ttu-id="092b4-119">構成プロファイル内で、デバイス制御ポリシーは次のセクションで定義されます。</span><span class="sxs-lookup"><span data-stu-id="092b4-119">Within the configuration profile, the device control policy is defined in the following section:</span></span>

|<span data-ttu-id="092b4-120">Section</span><span class="sxs-lookup"><span data-stu-id="092b4-120">Section</span></span>|<span data-ttu-id="092b4-121">値</span><span class="sxs-lookup"><span data-stu-id="092b4-121">Value</span></span>|
|:---|:---|
| <span data-ttu-id="092b4-122">**ドメイン**</span><span class="sxs-lookup"><span data-stu-id="092b4-122">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="092b4-123">**Key**</span><span class="sxs-lookup"><span data-stu-id="092b4-123">**Key**</span></span> | <span data-ttu-id="092b4-124">deviceControl</span><span class="sxs-lookup"><span data-stu-id="092b4-124">deviceControl</span></span> |
| <span data-ttu-id="092b4-125">**データ型**</span><span class="sxs-lookup"><span data-stu-id="092b4-125">**Data type**</span></span> | <span data-ttu-id="092b4-126">辞書 (入れ子になった基本設定)</span><span class="sxs-lookup"><span data-stu-id="092b4-126">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="092b4-127">**コメント**</span><span class="sxs-lookup"><span data-stu-id="092b4-127">**Comments**</span></span> | <span data-ttu-id="092b4-128">辞書の内容の説明については、以下のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="092b4-128">See the following sections for a description of the dictionary contents.</span></span> |

<span data-ttu-id="092b4-129">デバイス制御ポリシーは、次の場合に使用できます。</span><span class="sxs-lookup"><span data-stu-id="092b4-129">The device control policy can be used to:</span></span>

- [<span data-ttu-id="092b4-130">デバイス コントロールによって発生する通知の URL ターゲットをカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="092b4-130">Customize the URL target for notifications raised by device control</span></span>](#customize-url-target-for-notifications-raised-by-device-control)
- [<span data-ttu-id="092b4-131">リムーバブル デバイスを許可またはブロックする</span><span class="sxs-lookup"><span data-stu-id="092b4-131">Allow or block removable devices</span></span>](#allow-or-block-removable-devices)

### <a name="customize-url-target-for-notifications-raised-by-device-control"></a><span data-ttu-id="092b4-132">デバイスコントロールによって発生する通知の URL ターゲットをカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="092b4-132">Customize URL target for notifications raised by device control</span></span>

<span data-ttu-id="092b4-133">配置したデバイスコントロール ポリシーがデバイスに適用されている場合 (リムーバブル メディア デバイスへのアクセスが制限されているなど)、ユーザーに通知が表示されます。</span><span class="sxs-lookup"><span data-stu-id="092b4-133">When the device control policy that you have put in place is enforced on a device (for example, access to a removable media device is restricted), a notification is displayed to the user.</span></span>

![デバイス制御通知](images/mac-device-control-notification.png)

<span data-ttu-id="092b4-135">エンド ユーザーがこの通知をクリックすると、既定のブラウザーで Web ページが開きます。</span><span class="sxs-lookup"><span data-stu-id="092b4-135">When end users click this notification, a web page is opened in the default browser.</span></span> <span data-ttu-id="092b4-136">エンド ユーザーが通知をクリックするときに開く URL を構成できます。</span><span class="sxs-lookup"><span data-stu-id="092b4-136">You can configure the URL that is opened when end users click the notification.</span></span>

|<span data-ttu-id="092b4-137">Section</span><span class="sxs-lookup"><span data-stu-id="092b4-137">Section</span></span>|<span data-ttu-id="092b4-138">値</span><span class="sxs-lookup"><span data-stu-id="092b4-138">Value</span></span>|
|:---|:---|
| <span data-ttu-id="092b4-139">**ドメイン**</span><span class="sxs-lookup"><span data-stu-id="092b4-139">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="092b4-140">**Key**</span><span class="sxs-lookup"><span data-stu-id="092b4-140">**Key**</span></span> | <span data-ttu-id="092b4-141">navigationTarget</span><span class="sxs-lookup"><span data-stu-id="092b4-141">navigationTarget</span></span> |
| <span data-ttu-id="092b4-142">**データ型**</span><span class="sxs-lookup"><span data-stu-id="092b4-142">**Data type**</span></span> | <span data-ttu-id="092b4-143">String</span><span class="sxs-lookup"><span data-stu-id="092b4-143">String</span></span> |
| <span data-ttu-id="092b4-144">**コメント**</span><span class="sxs-lookup"><span data-stu-id="092b4-144">**Comments**</span></span> | <span data-ttu-id="092b4-145">定義されていない場合、製品は、製品が実行したアクションを説明する汎用ページを指す既定の URL を使用します。</span><span class="sxs-lookup"><span data-stu-id="092b4-145">If not defined, the product uses a default URL pointing to a generic page explaining the action taken by the product.</span></span> |

### <a name="allow-or-block-removable-devices"></a><span data-ttu-id="092b4-146">リムーバブル デバイスを許可またはブロックする</span><span class="sxs-lookup"><span data-stu-id="092b4-146">Allow or block removable devices</span></span>

<span data-ttu-id="092b4-147">デバイス制御ポリシーのリムーバブル メディア セクションは、リムーバブル メディアへのアクセスを制限するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="092b4-147">The removable media section of the device control policy is used to restrict access to removable media.</span></span> 

> [!NOTE]
> <span data-ttu-id="092b4-148">現在サポートされているリムーバブル メディアの種類は次のとおりです。ポリシーには USB ストレージ デバイスを含めできます。</span><span class="sxs-lookup"><span data-stu-id="092b4-148">The following types of removable media are currently supported and can be included in the policy: USB storage devices.</span></span>

|<span data-ttu-id="092b4-149">Section</span><span class="sxs-lookup"><span data-stu-id="092b4-149">Section</span></span>|<span data-ttu-id="092b4-150">値</span><span class="sxs-lookup"><span data-stu-id="092b4-150">Value</span></span>|
|:---|:---|
| <span data-ttu-id="092b4-151">**ドメイン**</span><span class="sxs-lookup"><span data-stu-id="092b4-151">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="092b4-152">**Key**</span><span class="sxs-lookup"><span data-stu-id="092b4-152">**Key**</span></span> | <span data-ttu-id="092b4-153">removableMediaPolicy</span><span class="sxs-lookup"><span data-stu-id="092b4-153">removableMediaPolicy</span></span> |
| <span data-ttu-id="092b4-154">**データ型**</span><span class="sxs-lookup"><span data-stu-id="092b4-154">**Data type**</span></span> | <span data-ttu-id="092b4-155">辞書 (入れ子になった基本設定)</span><span class="sxs-lookup"><span data-stu-id="092b4-155">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="092b4-156">**コメント**</span><span class="sxs-lookup"><span data-stu-id="092b4-156">**Comments**</span></span> | <span data-ttu-id="092b4-157">辞書の内容の説明については、以下のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="092b4-157">See the following sections for a description of the dictionary contents.</span></span> |

<span data-ttu-id="092b4-158">ポリシーのこのセクションは階層構造であり、柔軟性を最大限に高め、幅広い使用例をカバーします。</span><span class="sxs-lookup"><span data-stu-id="092b4-158">This section of the policy is hierarchical, allowing for maximum flexibility and covering a wide range of use cases.</span></span> <span data-ttu-id="092b4-159">トップ レベルでは、ベンダー ID によって識別されるベンダーです。</span><span class="sxs-lookup"><span data-stu-id="092b4-159">At the top level are vendors, identified by a vendor ID.</span></span> <span data-ttu-id="092b4-160">ベンダーごとに、製品 ID で識別される製品があります。</span><span class="sxs-lookup"><span data-stu-id="092b4-160">For each vendor, there are products, identified by a product ID.</span></span> <span data-ttu-id="092b4-161">最後に、製品ごとに、特定のデバイスを示すシリアル番号があります。</span><span class="sxs-lookup"><span data-stu-id="092b4-161">Finally, for each product there are serial numbers denoting specific devices.</span></span>

```
|-- policy top level 
    |-- vendor 1 
        |-- product 1 
            |-- serial number 1 
            ...
            |-- serial number N 
        ...
        |-- product N 
    ...
    |-- vendor N
```

<span data-ttu-id="092b4-162">デバイス識別子を検索する方法については、「デバイス識別子を検索 [する」を参照してください](#look-up-device-identifiers)。</span><span class="sxs-lookup"><span data-stu-id="092b4-162">For information on how to find the device identifiers, see [Look up device identifiers](#look-up-device-identifiers).</span></span>

<span data-ttu-id="092b4-163">ポリシーは、最も具体的なエントリから最も一般的なエントリに評価されます。</span><span class="sxs-lookup"><span data-stu-id="092b4-163">The policy is evaluated from the most specific entry to the most general one.</span></span> <span data-ttu-id="092b4-164">つまり、デバイスが接続されている場合、製品は、各リムーバブル メディア デバイスのポリシーで最も具体的な一致を検索し、そのレベルでアクセス許可を適用します。</span><span class="sxs-lookup"><span data-stu-id="092b4-164">Meaning, when a device is plugged in, the product tries to find the most specific match in the policy for each removable media device and apply the permissions at that level.</span></span> <span data-ttu-id="092b4-165">一致しない場合は、デバイスがポリシー内の他のエントリと一致しない場合の既定値である、トップ レベルで指定されたアクセス許可に対して、次の最適な一致が適用されます。</span><span class="sxs-lookup"><span data-stu-id="092b4-165">If there is no match, then the next best match is applied, all the way to the permission specified at the top level, which is the default when a device does not match any other entry in the policy.</span></span>

#### <a name="policy-enforcement-level"></a><span data-ttu-id="092b4-166">ポリシーの適用レベル</span><span class="sxs-lookup"><span data-stu-id="092b4-166">Policy enforcement level</span></span>

<span data-ttu-id="092b4-167">[リムーバブル メディア] セクションの下には、適用レベルを設定するオプションがあります。このオプションでは、次のいずれかの値を使用できます。</span><span class="sxs-lookup"><span data-stu-id="092b4-167">Under the removable media section, there is an option to set the enforcement level, which can take one of the following values:</span></span>

- <span data-ttu-id="092b4-168">`audit` - この適用レベルでは、デバイスへのアクセスが制限されている場合、ユーザーに通知が表示されます。ただし、デバイスは引き続き使用できます。</span><span class="sxs-lookup"><span data-stu-id="092b4-168">`audit` - Under this enforcement level, if access to a device is restricted, a notification is displayed to the user, however the device can still be used.</span></span> <span data-ttu-id="092b4-169">この適用レベルは、ポリシーの有効性を評価するために役立ちます。</span><span class="sxs-lookup"><span data-stu-id="092b4-169">This enforcement level can be useful to evaluate the effectiveness of a policy.</span></span>
- <span data-ttu-id="092b4-170">`block` - この適用レベルでは、ユーザーがデバイスで実行できる操作は、ポリシーで定義されている操作に制限されます。</span><span class="sxs-lookup"><span data-stu-id="092b4-170">`block` - Under this enforcement level, the operations that the user can perform on the device are limited to what is defined in the policy.</span></span> <span data-ttu-id="092b4-171">さらに、ユーザーに通知が発生します。</span><span class="sxs-lookup"><span data-stu-id="092b4-171">Furthermore, a notification is raised to the user.</span></span> 

> [!NOTE] 
> <span data-ttu-id="092b4-172">既定では、適用レベルは に設定されています `audit` 。</span><span class="sxs-lookup"><span data-stu-id="092b4-172">By default, the enforcement level is set to `audit`.</span></span> 

|<span data-ttu-id="092b4-173">Section</span><span class="sxs-lookup"><span data-stu-id="092b4-173">Section</span></span>|<span data-ttu-id="092b4-174">値</span><span class="sxs-lookup"><span data-stu-id="092b4-174">Value</span></span>|
|:---|:---|
| <span data-ttu-id="092b4-175">**ドメイン**</span><span class="sxs-lookup"><span data-stu-id="092b4-175">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="092b4-176">**Key**</span><span class="sxs-lookup"><span data-stu-id="092b4-176">**Key**</span></span> | <span data-ttu-id="092b4-177">enforcementLevel</span><span class="sxs-lookup"><span data-stu-id="092b4-177">enforcementLevel</span></span> |
| <span data-ttu-id="092b4-178">**データ型**</span><span class="sxs-lookup"><span data-stu-id="092b4-178">**Data type**</span></span> | <span data-ttu-id="092b4-179">String</span><span class="sxs-lookup"><span data-stu-id="092b4-179">String</span></span> |
| <span data-ttu-id="092b4-180">**指定可能な値**</span><span class="sxs-lookup"><span data-stu-id="092b4-180">**Possible values**</span></span> | <span data-ttu-id="092b4-181">監査 (既定)</span><span class="sxs-lookup"><span data-stu-id="092b4-181">audit (default)</span></span> <br/> <span data-ttu-id="092b4-182">block</span><span class="sxs-lookup"><span data-stu-id="092b4-182">block</span></span> |

#### <a name="default-permission-level"></a><span data-ttu-id="092b4-183">既定のアクセス許可レベル</span><span class="sxs-lookup"><span data-stu-id="092b4-183">Default permission level</span></span>

<span data-ttu-id="092b4-184">[リムーバブル メディア] セクションのトップ レベルで、ポリシー内の他のアクセス許可と一致しないデバイスの既定のアクセス許可レベルを構成できます。</span><span class="sxs-lookup"><span data-stu-id="092b4-184">At the top level of the removable media section, you can configure the default permission level for devices that do not match anything else in the policy.</span></span>

<span data-ttu-id="092b4-185">この設定は、次の値に設定できます。</span><span class="sxs-lookup"><span data-stu-id="092b4-185">This setting can be set to:</span></span>

- <span data-ttu-id="092b4-186">`none` - デバイスで操作を実行できません</span><span class="sxs-lookup"><span data-stu-id="092b4-186">`none` - No operations can be performed on the device</span></span>
- <span data-ttu-id="092b4-187">次の値の組み合わせ。</span><span class="sxs-lookup"><span data-stu-id="092b4-187">A combination of the following values:</span></span>
    - <span data-ttu-id="092b4-188">`read` - デバイスで読み取り操作が許可されている</span><span class="sxs-lookup"><span data-stu-id="092b4-188">`read` - Read operations are permitted on the device</span></span>
    - <span data-ttu-id="092b4-189">`write` - デバイスで書き込み操作が許可されている</span><span class="sxs-lookup"><span data-stu-id="092b4-189">`write` - Write operations are permitted on the device</span></span>
    - <span data-ttu-id="092b4-190">`execute` - デバイスで実行操作が許可されている</span><span class="sxs-lookup"><span data-stu-id="092b4-190">`execute` - Execute operations are permitted on the device</span></span>

> [!NOTE]
> <span data-ttu-id="092b4-191">アクセス `none` 許可レベルに存在する場合、他のアクセス許可 ( `read` 、 、 、 ) `write` `execute` は無視されます。</span><span class="sxs-lookup"><span data-stu-id="092b4-191">If `none` is present in the permission level, any other permissions (`read`, `write`, or `execute`) will be ignored.</span></span>

> [!NOTE]
> <span data-ttu-id="092b4-192">この `execute` アクセス許可は、Mach-O バイナリの実行のみを参照します。</span><span class="sxs-lookup"><span data-stu-id="092b4-192">The `execute` permission only refers to execution of Mach-O binaries.</span></span> <span data-ttu-id="092b4-193">スクリプトの実行や他の種類のペイロードは含めではありません。</span><span class="sxs-lookup"><span data-stu-id="092b4-193">It does not include execution of scripts or other types of payloads.</span></span>

|<span data-ttu-id="092b4-194">Section</span><span class="sxs-lookup"><span data-stu-id="092b4-194">Section</span></span>|<span data-ttu-id="092b4-195">値</span><span class="sxs-lookup"><span data-stu-id="092b4-195">Value</span></span>|
|:---|:---|
| <span data-ttu-id="092b4-196">**ドメイン**</span><span class="sxs-lookup"><span data-stu-id="092b4-196">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="092b4-197">**Key**</span><span class="sxs-lookup"><span data-stu-id="092b4-197">**Key**</span></span> | <span data-ttu-id="092b4-198">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="092b4-198">permission</span></span> |
| <span data-ttu-id="092b4-199">**データ型**</span><span class="sxs-lookup"><span data-stu-id="092b4-199">**Data type**</span></span> | <span data-ttu-id="092b4-200">文字列の配列</span><span class="sxs-lookup"><span data-stu-id="092b4-200">Array of strings</span></span> |
| <span data-ttu-id="092b4-201">**可能な値**</span><span class="sxs-lookup"><span data-stu-id="092b4-201">**Possible values**</span></span> | <span data-ttu-id="092b4-202">none</span><span class="sxs-lookup"><span data-stu-id="092b4-202">none</span></span> <br/> <span data-ttu-id="092b4-203">read</span><span class="sxs-lookup"><span data-stu-id="092b4-203">read</span></span> <br/> <span data-ttu-id="092b4-204">write</span><span class="sxs-lookup"><span data-stu-id="092b4-204">write</span></span> <br/> <span data-ttu-id="092b4-205">execute</span><span class="sxs-lookup"><span data-stu-id="092b4-205">execute</span></span> |

#### <a name="restrict-removable-media-by-vendor-product-and-serial-number"></a><span data-ttu-id="092b4-206">ベンダー、製品、シリアル番号によってリムーバブル メディアを制限する</span><span class="sxs-lookup"><span data-stu-id="092b4-206">Restrict removable media by vendor, product, and serial number</span></span>

<span data-ttu-id="092b4-207">「リムーバブル デバイス [を許可またはブロック](#allow-or-block-removable-devices)する」で説明したように、USB デバイスなどのリムーバブル メディアは、ベンダー ID、製品 ID、シリアル番号で識別できます。</span><span class="sxs-lookup"><span data-stu-id="092b4-207">As described in [Allow or block removable devices](#allow-or-block-removable-devices), removable media such as USB devices can be identified by the vendor ID, product ID, and serial number.</span></span>

<span data-ttu-id="092b4-208">リムーバブル メディア ポリシーのトップ レベルでは、ベンダー レベルで詳細な制限を必要に応じて定義できます。</span><span class="sxs-lookup"><span data-stu-id="092b4-208">At the top level of the removable media policy, you can optionally define more granular restrictions at the vendor level.</span></span> 

<span data-ttu-id="092b4-209">ディクショナリ `vendors` には 1 つ以上のエントリが含まれるので、各エントリはベンダー ID で識別されます。</span><span class="sxs-lookup"><span data-stu-id="092b4-209">The `vendors` dictionary contains one or more entries, with each entry being identified by the vendor ID.</span></span>

|<span data-ttu-id="092b4-210">Section</span><span class="sxs-lookup"><span data-stu-id="092b4-210">Section</span></span>|<span data-ttu-id="092b4-211">値</span><span class="sxs-lookup"><span data-stu-id="092b4-211">Value</span></span>|
|:---|:---|
| <span data-ttu-id="092b4-212">**ドメイン**</span><span class="sxs-lookup"><span data-stu-id="092b4-212">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="092b4-213">**Key**</span><span class="sxs-lookup"><span data-stu-id="092b4-213">**Key**</span></span> | <span data-ttu-id="092b4-214">ベンダー</span><span class="sxs-lookup"><span data-stu-id="092b4-214">vendors</span></span> |
| <span data-ttu-id="092b4-215">**データ型**</span><span class="sxs-lookup"><span data-stu-id="092b4-215">**Data type**</span></span> | <span data-ttu-id="092b4-216">辞書 (入れ子になった基本設定)</span><span class="sxs-lookup"><span data-stu-id="092b4-216">Dictionary (nested preference)</span></span> |

<span data-ttu-id="092b4-217">ベンダーごとに、そのベンダーのデバイスに必要なアクセス許可レベルを指定できます。</span><span class="sxs-lookup"><span data-stu-id="092b4-217">For each vendor, you can specify the desired permission level for devices from that vendor.</span></span>

|<span data-ttu-id="092b4-218">Section</span><span class="sxs-lookup"><span data-stu-id="092b4-218">Section</span></span>|<span data-ttu-id="092b4-219">値</span><span class="sxs-lookup"><span data-stu-id="092b4-219">Value</span></span>|
|:---|:---|
| <span data-ttu-id="092b4-220">**ドメイン**</span><span class="sxs-lookup"><span data-stu-id="092b4-220">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="092b4-221">**Key**</span><span class="sxs-lookup"><span data-stu-id="092b4-221">**Key**</span></span> | <span data-ttu-id="092b4-222">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="092b4-222">permission</span></span> |
| <span data-ttu-id="092b4-223">**データ型**</span><span class="sxs-lookup"><span data-stu-id="092b4-223">**Data type**</span></span> | <span data-ttu-id="092b4-224">文字列の配列</span><span class="sxs-lookup"><span data-stu-id="092b4-224">Array of strings</span></span> |
| <span data-ttu-id="092b4-225">**可能な値**</span><span class="sxs-lookup"><span data-stu-id="092b4-225">**Possible values**</span></span> | <span data-ttu-id="092b4-226">既定のアクセス [許可レベルと同じ](#default-permission-level)</span><span class="sxs-lookup"><span data-stu-id="092b4-226">Same as [Default permission level](#default-permission-level)</span></span> |

<span data-ttu-id="092b4-227">さらに、必要に応じて、より詳細なアクセス許可が定義されているベンダーに属する製品のセットを指定できます。</span><span class="sxs-lookup"><span data-stu-id="092b4-227">Furthermore, you can optionally specify the set of products belonging to that vendor for which more granular permissions are defined.</span></span> <span data-ttu-id="092b4-228">ディクショナリ `products` には 1 つ以上のエントリが含まれるので、各エントリは製品 ID で識別されます。</span><span class="sxs-lookup"><span data-stu-id="092b4-228">The `products` dictionary contains one or more entries, with each entry being identified by the product ID.</span></span> 

|<span data-ttu-id="092b4-229">Section</span><span class="sxs-lookup"><span data-stu-id="092b4-229">Section</span></span>|<span data-ttu-id="092b4-230">値</span><span class="sxs-lookup"><span data-stu-id="092b4-230">Value</span></span>|
|:---|:---|
| <span data-ttu-id="092b4-231">**ドメイン**</span><span class="sxs-lookup"><span data-stu-id="092b4-231">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="092b4-232">**Key**</span><span class="sxs-lookup"><span data-stu-id="092b4-232">**Key**</span></span> | <span data-ttu-id="092b4-233">製品</span><span class="sxs-lookup"><span data-stu-id="092b4-233">products</span></span> |
| <span data-ttu-id="092b4-234">**データ型**</span><span class="sxs-lookup"><span data-stu-id="092b4-234">**Data type**</span></span> | <span data-ttu-id="092b4-235">辞書 (入れ子になった基本設定)</span><span class="sxs-lookup"><span data-stu-id="092b4-235">Dictionary (nested preference)</span></span> |

<span data-ttu-id="092b4-236">製品ごとに、その製品の目的のアクセス許可レベルを指定できます。</span><span class="sxs-lookup"><span data-stu-id="092b4-236">For each product, you can specify the desired permission level for that product.</span></span>

|<span data-ttu-id="092b4-237">Section</span><span class="sxs-lookup"><span data-stu-id="092b4-237">Section</span></span>|<span data-ttu-id="092b4-238">値</span><span class="sxs-lookup"><span data-stu-id="092b4-238">Value</span></span>|
|:---|:---|
| <span data-ttu-id="092b4-239">**ドメイン**</span><span class="sxs-lookup"><span data-stu-id="092b4-239">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="092b4-240">**Key**</span><span class="sxs-lookup"><span data-stu-id="092b4-240">**Key**</span></span> | <span data-ttu-id="092b4-241">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="092b4-241">permission</span></span> |
| <span data-ttu-id="092b4-242">**データ型**</span><span class="sxs-lookup"><span data-stu-id="092b4-242">**Data type**</span></span> | <span data-ttu-id="092b4-243">文字列の配列</span><span class="sxs-lookup"><span data-stu-id="092b4-243">Array of strings</span></span> |
| <span data-ttu-id="092b4-244">**可能な値**</span><span class="sxs-lookup"><span data-stu-id="092b4-244">**Possible values**</span></span> | <span data-ttu-id="092b4-245">既定のアクセス [許可レベルと同じ](#default-permission-level)</span><span class="sxs-lookup"><span data-stu-id="092b4-245">Same as [Default permission level](#default-permission-level)</span></span> |

<span data-ttu-id="092b4-246">さらに、より詳細なアクセス許可が定義されているシリアル番号のオプション セットを指定できます。</span><span class="sxs-lookup"><span data-stu-id="092b4-246">Furthermore, you can specify an optional set of serial numbers for which more granular permissions are defined.</span></span>

<span data-ttu-id="092b4-247">辞書 `serialNumbers` には 1 つ以上のエントリが含まれるので、各エントリはシリアル番号で識別されます。</span><span class="sxs-lookup"><span data-stu-id="092b4-247">The `serialNumbers` dictionary contains one or more entries, with each entry being identified by the serial number.</span></span>

|<span data-ttu-id="092b4-248">Section</span><span class="sxs-lookup"><span data-stu-id="092b4-248">Section</span></span>|<span data-ttu-id="092b4-249">値</span><span class="sxs-lookup"><span data-stu-id="092b4-249">Value</span></span>|
|:---|:---|
| <span data-ttu-id="092b4-250">**ドメイン**</span><span class="sxs-lookup"><span data-stu-id="092b4-250">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="092b4-251">**Key**</span><span class="sxs-lookup"><span data-stu-id="092b4-251">**Key**</span></span> | <span data-ttu-id="092b4-252">serialNumbers</span><span class="sxs-lookup"><span data-stu-id="092b4-252">serialNumbers</span></span> |
| <span data-ttu-id="092b4-253">**データ型**</span><span class="sxs-lookup"><span data-stu-id="092b4-253">**Data type**</span></span> | <span data-ttu-id="092b4-254">辞書 (入れ子になった基本設定)</span><span class="sxs-lookup"><span data-stu-id="092b4-254">Dictionary (nested preference)</span></span> |

<span data-ttu-id="092b4-255">シリアル番号ごとに、目的のアクセス許可レベルを指定できます。</span><span class="sxs-lookup"><span data-stu-id="092b4-255">For each serial number, you can specify the desired permission level.</span></span>

|<span data-ttu-id="092b4-256">Section</span><span class="sxs-lookup"><span data-stu-id="092b4-256">Section</span></span>|<span data-ttu-id="092b4-257">値</span><span class="sxs-lookup"><span data-stu-id="092b4-257">Value</span></span>|
|:---|:---|
| <span data-ttu-id="092b4-258">**ドメイン**</span><span class="sxs-lookup"><span data-stu-id="092b4-258">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="092b4-259">**Key**</span><span class="sxs-lookup"><span data-stu-id="092b4-259">**Key**</span></span> | <span data-ttu-id="092b4-260">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="092b4-260">permission</span></span> |
| <span data-ttu-id="092b4-261">**データ型**</span><span class="sxs-lookup"><span data-stu-id="092b4-261">**Data type**</span></span> | <span data-ttu-id="092b4-262">文字列の配列</span><span class="sxs-lookup"><span data-stu-id="092b4-262">Array of strings</span></span> |
| <span data-ttu-id="092b4-263">**可能な値**</span><span class="sxs-lookup"><span data-stu-id="092b4-263">**Possible values**</span></span> | <span data-ttu-id="092b4-264">既定のアクセス [許可レベルと同じ](#default-permission-level)</span><span class="sxs-lookup"><span data-stu-id="092b4-264">Same as [Default permission level](#default-permission-level)</span></span> |

#### <a name="example-device-control-policy"></a><span data-ttu-id="092b4-265">デバイス制御ポリシーの例</span><span class="sxs-lookup"><span data-stu-id="092b4-265">Example device control policy</span></span>

<span data-ttu-id="092b4-266">次の例は、上記のすべての概念をデバイス制御ポリシーに組み合わせる方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="092b4-266">The following example shows how all of the above concepts can be combined into a device control policy.</span></span> <span data-ttu-id="092b4-267">次の例では、リムーバブル メディア ポリシーの階層的な性質に注意してください。</span><span class="sxs-lookup"><span data-stu-id="092b4-267">In the following example, note the hierarchical nature of the removable media policy.</span></span>

```xml
<?xml version="1.0" encoding="UTF-8"?> 
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd"> 
<plist version="1.0"> 
<dict> 
    <key>deviceControl</key> 
    <dict> 
        <key>navigationTarget</key> 
        <string>[custom URL for notifications]</string> 
        <key>removableMediaPolicy</key> 
        <dict> 
            <key>enforcementLevel</key> 
            <string>[enforcement level]</string> <!-- audit / block --> 
            <key>permission</key> 
            <array> 
                <string>[permission]</string> <!-- none / read / write / execute --> 
                <!-- other permissions -->
            </array> 
            <key>vendors</key> 
            <dict> 
                <key>[vendor id]</key> 
                <dict>
                    <key>permission</key> 
                    <array> 
                        <string>[permission]</string> <!-- none / read / write / execute --> 
                        <!-- other permissions -->
                    </array> 
                    <key>products</key> 
                    <dict> 
                        <key>[product id]</key> 
                        <dict> 
                            <key>permission</key> 
                            <array> 
                                <string>[permission]</string> <!-- none / read / write / execute --> 
                                <!-- other permissions -->
                            </array> 
                            <key>serialNumbers</key> 
                            <dict> 
                                <key>[serial-number]</key> 
                                <array> 
                                    <string>[permission]</string> <!-- none / read / write / execute --> 
                                    <!-- other permissions -->
                                </array> 
                                <!-- other serial numbers --> 
                            </dict> 
                        </dict> 
                        <!-- other products --> 
                    </dict> 
                </dict> 
                <!-- other vendors --> 
            </dict> 
        </dict> 
    </dict> 
</dict> 
</plist> 
```

<span data-ttu-id="092b4-268">次のドキュメントには、デバイス制御ポリシーのその他の例が含まれています。</span><span class="sxs-lookup"><span data-stu-id="092b4-268">We have included more examples of device control policies in the following documents:</span></span>

- [<span data-ttu-id="092b4-269">Intune のデバイス制御ポリシーの例</span><span class="sxs-lookup"><span data-stu-id="092b4-269">Examples of device control policies for Intune</span></span>](mac-device-control-intune.md)
- [<span data-ttu-id="092b4-270">JAMF のデバイス制御ポリシーの例</span><span class="sxs-lookup"><span data-stu-id="092b4-270">Examples of device control policies for JAMF</span></span>](mac-device-control-jamf.md)

#### <a name="look-up-device-identifiers"></a><span data-ttu-id="092b4-271">デバイス識別子の参照</span><span class="sxs-lookup"><span data-stu-id="092b4-271">Look up device identifiers</span></span>

<span data-ttu-id="092b4-272">USB デバイスのベンダー ID、製品 ID、シリアル番号を確認するには、次の方法を実行します。</span><span class="sxs-lookup"><span data-stu-id="092b4-272">To find the vendor ID, product ID, and serial number of a USB device:</span></span>

1. <span data-ttu-id="092b4-273">Mac デバイスにログインします。</span><span class="sxs-lookup"><span data-stu-id="092b4-273">Log into a Mac device.</span></span>
1. <span data-ttu-id="092b4-274">識別子を参照する USB デバイスを接続します。</span><span class="sxs-lookup"><span data-stu-id="092b4-274">Plug in the USB device for which you want to look up the identifiers.</span></span>
1. <span data-ttu-id="092b4-275">macOS のトップ レベル メニューで、[この Mac について **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="092b4-275">In the top-level menu of macOS, select **About This Mac**.</span></span>

    ![この Mac について](images/mac-device-control-lookup-1.png)

1. <span data-ttu-id="092b4-277">[システム **レポート] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="092b4-277">Select **System Report**.</span></span>

    ![システム レポート](images/mac-device-control-lookup-2.png)

1. <span data-ttu-id="092b4-279">左側の列から **[USB] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="092b4-279">From the left column, select **USB**.</span></span>

    ![すべての USB デバイスの表示](images/mac-device-control-lookup-3.png)

1. <span data-ttu-id="092b4-281">[USB **デバイス ツリー]** で、接続した USB デバイスに移動します。</span><span class="sxs-lookup"><span data-stu-id="092b4-281">Under **USB Device Tree**, navigate to the USB device that you plugged in.</span></span>

    ![USB デバイスの詳細](images/mac-device-control-lookup-4.png)

1. <span data-ttu-id="092b4-283">ベンダー ID、製品 ID、シリアル番号が表示されます。</span><span class="sxs-lookup"><span data-stu-id="092b4-283">The vendor ID, product ID, and serial number are displayed.</span></span> <span data-ttu-id="092b4-284">ベンダー ID と製品 ID をリムーバブル メディア ポリシーに追加する場合は、後にパーツを追加する必要があります `0x` 。</span><span class="sxs-lookup"><span data-stu-id="092b4-284">When adding the vendor ID and product ID to the removable media policy, you must only add the part after `0x`.</span></span> <span data-ttu-id="092b4-285">たとえば、次の図では、ベンダー ID は、 `1000` 製品 ID は `090c` です。</span><span class="sxs-lookup"><span data-stu-id="092b4-285">For example, in the below image, vendor ID is `1000` and product ID is `090c`.</span></span>

#### <a name="discover-usb-devices-in-your-organization"></a><span data-ttu-id="092b4-286">組織内の USB デバイスを検出する</span><span class="sxs-lookup"><span data-stu-id="092b4-286">Discover USB devices in your organization</span></span>

<span data-ttu-id="092b4-287">Microsoft Defender for Endpoint Advanced Hunting で、USB デバイスから発生するマウント、マウント解除、およびボリューム変更イベントを表示できます。</span><span class="sxs-lookup"><span data-stu-id="092b4-287">You can view mount, unmount, and volume change events originating from USB devices in Microsoft Defender for Endpoint advanced hunting.</span></span> <span data-ttu-id="092b4-288">これらのイベントは、疑わしい利用状況を特定したり、内部調査を実行したりするのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="092b4-288">These events can be helpful to identify suspicious usage activity or perform internal investigations.</span></span>

```
DeviceEvents 
    | where ActionType == "UsbDriveMounted" or ActionType == "UsbDriveUnmounted" or ActionType == "UsbDriveDriveLetterChanged"
    | where DeviceId == "<device ID>"
```

## <a name="device-control-policy-deployment"></a><span data-ttu-id="092b4-289">デバイス制御ポリシーの展開</span><span class="sxs-lookup"><span data-stu-id="092b4-289">Device control policy deployment</span></span>

<span data-ttu-id="092b4-290">macOS での Microsoft Defender for Endpoint の設定の説明に従って、デバイス制御ポリシーを他の製品設定の横 [に含める必要があります](mac-preferences.md)。</span><span class="sxs-lookup"><span data-stu-id="092b4-290">The device control policy must be included next to the other product settings, as described in [Set preferences for Microsoft Defender for Endpoint on macOS](mac-preferences.md).</span></span>

<span data-ttu-id="092b4-291">このプロファイルは、「構成プロファイルの展開」に記載されている手順 [を使用して展開できます](mac-preferences.md#configuration-profile-deployment)。</span><span class="sxs-lookup"><span data-stu-id="092b4-291">This profile can be deployed using the instructions listed in [Configuration profile deployment](mac-preferences.md#configuration-profile-deployment).</span></span>

## <a name="troubleshooting-tips"></a><span data-ttu-id="092b4-292">トラブルシューティングのヒント</span><span class="sxs-lookup"><span data-stu-id="092b4-292">Troubleshooting tips</span></span>

<span data-ttu-id="092b4-293">Intune または JAMF を介して構成プロファイルをプッシュした後、ターミナルから次のコマンドを実行して、製品によって正常にピックアップされたのか確認できます。</span><span class="sxs-lookup"><span data-stu-id="092b4-293">After pushing the configuration profile through Intune or JAMF, you can check if it was successfully picked up by the product by running the following command from the Terminal:</span></span>

```bash
mdatp device-control removable-media policy list
```

<span data-ttu-id="092b4-294">このコマンドは、製品が使用しているデバイス制御ポリシーを標準出力に出力します。</span><span class="sxs-lookup"><span data-stu-id="092b4-294">This command will print to standard output the device control policy that the product is using.</span></span> <span data-ttu-id="092b4-295">この印刷を行う場合は、(a) 構成プロファイルが実際に管理コンソールからデバイスにプッシュされ、(b) このドキュメントで説明するように、有効なデバイス制御ポリシーを使用してください。 `Policy is empty`</span><span class="sxs-lookup"><span data-stu-id="092b4-295">In case this prints `Policy is empty`, make sure that (a) the configuration profile has indeed been pushed to your device from the management console, and (b) it is a valid device control policy, as described in this document.</span></span>

<span data-ttu-id="092b4-296">ポリシーが正常に配信され、1 つ以上のデバイスが接続されているデバイスで、次のコマンドを実行して、すべてのデバイスと、ポリシーに適用される有効なアクセス許可を一覧表示できます。</span><span class="sxs-lookup"><span data-stu-id="092b4-296">On a device where the policy has been delivered successfully and where there are one or more devices plugged in, you can run the following command to list all devices and the effective permissions applied to them.</span></span>

```bash
mdatp device-control removable-media devices list
```

<span data-ttu-id="092b4-297">出力例 :</span><span class="sxs-lookup"><span data-stu-id="092b4-297">Example of output:</span></span>

```Output
.Device(s)
|-o Name: Untitled 1, Permission ["read", "execute"]
| |-o Vendor: General "fff0"
| |-o Product: USB Flash Disk "1000"
| |-o Serial number: "04ZSSMHI2O7WBVOA"
| |-o Mount point: "/Volumes/TESTUSB"
```

<span data-ttu-id="092b4-298">上記の例では、デバイスに配信されたデバイス制御ポリシーに従って、接続されているリムーバブル メディア デバイスが 1 つしか接続され、アクセス許可が `read` `execute` 付与されています。</span><span class="sxs-lookup"><span data-stu-id="092b4-298">In the above example, there is only one removable media device plugged in and it has `read` and `execute` permissions, according to the device control policy that was delivered to the device.</span></span>

## <a name="related-topics"></a><span data-ttu-id="092b4-299">関連項目</span><span class="sxs-lookup"><span data-stu-id="092b4-299">Related topics</span></span>

- [<span data-ttu-id="092b4-300">Intune のデバイス制御ポリシーの例</span><span class="sxs-lookup"><span data-stu-id="092b4-300">Examples of device control policies for Intune</span></span>](mac-device-control-intune.md)
- [<span data-ttu-id="092b4-301">JAMF のデバイス制御ポリシーの例</span><span class="sxs-lookup"><span data-stu-id="092b4-301">Examples of device control policies for JAMF</span></span>](mac-device-control-jamf.md)
