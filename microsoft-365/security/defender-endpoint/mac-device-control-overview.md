---
title: macOS のデバイスコントロール
description: USB デバイスなどのリムーバブル 記憶域からの脅威を軽減するために Microsoft Defender for Endpoint for Mac を構成する方法について説明します。
keywords: microsoft, defender, atp, mac, device, control, usb, リムーバブル, メディア
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
ms.openlocfilehash: 098eb30764870e69c5b1b6c2cec3cf8e5cb11691
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2021
ms.locfileid: "51186571"
---
# <a name="device-control-for-macos"></a><span data-ttu-id="ccf85-104">macOS のデバイスコントロール</span><span class="sxs-lookup"><span data-stu-id="ccf85-104">Device control for macOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="ccf85-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="ccf85-105">**Applies to:**</span></span>
- [<span data-ttu-id="ccf85-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="ccf85-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="ccf85-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ccf85-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="ccf85-108">Microsoft Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="ccf85-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="ccf85-109">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="ccf85-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="requirements"></a><span data-ttu-id="ccf85-110">要件</span><span class="sxs-lookup"><span data-stu-id="ccf85-110">Requirements</span></span>

<span data-ttu-id="ccf85-111">macOS のデバイスコントロールには、次の前提条件があります。</span><span class="sxs-lookup"><span data-stu-id="ccf85-111">Device control for macOS has the following prerequisites:</span></span>

>[!div class="checklist"]
> - <span data-ttu-id="ccf85-112">Microsoft Defender for Endpoint の資格 (試用版の場合があります)</span><span class="sxs-lookup"><span data-stu-id="ccf85-112">Microsoft Defender for Endpoint entitlement (can be trial)</span></span>
> - <span data-ttu-id="ccf85-113">最小 OS バージョン: macOS 10.15.4 以上</span><span class="sxs-lookup"><span data-stu-id="ccf85-113">Minimum OS version: macOS 10.15.4 or higher</span></span>
> - <span data-ttu-id="ccf85-114">最小製品バージョン: 101.24.59</span><span class="sxs-lookup"><span data-stu-id="ccf85-114">Minimum product version: 101.24.59</span></span>
> - <span data-ttu-id="ccf85-115">デバイスがシステム拡張機能で実行されている必要があります (これは macOS 11 Big Sur の既定値です)。</span><span class="sxs-lookup"><span data-stu-id="ccf85-115">Your device must be running with system extensions (this is the default on macOS 11 Big Sur).</span></span> 
> 
>   <span data-ttu-id="ccf85-116">次のコマンドを実行して、デバイスがシステム拡張機能で実行されているのを確認し、コンソールに印刷 `endpoint_security_extension` されているのを確認できます。</span><span class="sxs-lookup"><span data-stu-id="ccf85-116">You can check if your device is running on system extensions by running the following command and verify that it is printing `endpoint_security_extension` to the console:</span></span> 
> 
>   ```bash
>   mdatp health --field real_time_protection_subsystem 
>   ```
> - <span data-ttu-id="ccf85-117">デバイスが Microsoft AutoUpdate 更新チャネル (以前に呼び出 `Beta` `InsiderFast` された) にある必要があります。</span><span class="sxs-lookup"><span data-stu-id="ccf85-117">Your device must be in `Beta` (previously called `InsiderFast`) Microsoft AutoUpdate update channel.</span></span> <span data-ttu-id="ccf85-118">詳細については [、「Deploy updates for Microsoft Defender for Endpoint for Mac」を参照してください](mac-updates.md)。</span><span class="sxs-lookup"><span data-stu-id="ccf85-118">For more information, see [Deploy updates for Microsoft Defender for Endpoint for Mac](mac-updates.md).</span></span>
> 
>   <span data-ttu-id="ccf85-119">次のコマンドを使用して更新チャネルを確認できます。</span><span class="sxs-lookup"><span data-stu-id="ccf85-119">You can check the update channel using the following command:</span></span> 
> 
>    ```bash
>    mdatp health --field release_ring 
>    ```
>
>    <span data-ttu-id="ccf85-120">上記のコマンドが印刷されない場合、またはターミナルから次の `Beta` `InsiderFast` コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="ccf85-120">If the above command does not print either `Beta` or `InsiderFast`, execute the following command from the Terminal.</span></span> <span data-ttu-id="ccf85-121">チャネル更新プログラムは、次に製品が起動するときに有効になります (次の製品更新プログラムがインストールされている場合、またはデバイスが再起動された場合)。</span><span class="sxs-lookup"><span data-stu-id="ccf85-121">The channel update takes effect next time the product starts (when the next product update is installed or when the device is rebooted).</span></span> 
> 
>    ```bash
>    defaults write com.microsoft.autoupdate2 ChannelName -string Beta
>    ```
>
>    <span data-ttu-id="ccf85-122">または、管理環境 (JAMF または Intune) にある場合は、更新プログラム チャネルをリモートで構成できます。</span><span class="sxs-lookup"><span data-stu-id="ccf85-122">Alternatively, if you are in a managed environment (JAMF or Intune), you can configure the update channel remotely.</span></span> <span data-ttu-id="ccf85-123">詳細については [、「Deploy updates for Microsoft Defender for Endpoint for Mac」を参照してください](mac-updates.md)。</span><span class="sxs-lookup"><span data-stu-id="ccf85-123">For more information, see [Deploy updates for Microsoft Defender for Endpoint for Mac](mac-updates.md).</span></span> 

## <a name="device-control-policy"></a><span data-ttu-id="ccf85-124">デバイス制御ポリシー</span><span class="sxs-lookup"><span data-stu-id="ccf85-124">Device control policy</span></span>

<span data-ttu-id="ccf85-125">macOS のデバイスコントロールを構成するには、組織内で設定する制限を説明するポリシーを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ccf85-125">To configure device control for macOS, you must create a policy that describes the restrictions you want to put in place within your organization.</span></span>

<span data-ttu-id="ccf85-126">デバイス制御ポリシーは、他のすべての製品設定を構成するために使用される構成プロファイルに含まれています。</span><span class="sxs-lookup"><span data-stu-id="ccf85-126">The device control policy is included in the configuration profile used to configure all other product settings.</span></span> <span data-ttu-id="ccf85-127">詳細については、「構成プロファイル [構造」を参照してください](mac-preferences.md#configuration-profile-structure)。</span><span class="sxs-lookup"><span data-stu-id="ccf85-127">For more information, see [Configuration profile structure](mac-preferences.md#configuration-profile-structure).</span></span>

<span data-ttu-id="ccf85-128">構成プロファイル内で、デバイス制御ポリシーは次のセクションで定義されます。</span><span class="sxs-lookup"><span data-stu-id="ccf85-128">Within the configuration profile, the device control policy is defined in the following section:</span></span>

|||
|:---|:---|
| <span data-ttu-id="ccf85-129">**ドメイン**</span><span class="sxs-lookup"><span data-stu-id="ccf85-129">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="ccf85-130">**キー**</span><span class="sxs-lookup"><span data-stu-id="ccf85-130">**Key**</span></span> | <span data-ttu-id="ccf85-131">deviceControl</span><span class="sxs-lookup"><span data-stu-id="ccf85-131">deviceControl</span></span> |
| <span data-ttu-id="ccf85-132">**データ型**</span><span class="sxs-lookup"><span data-stu-id="ccf85-132">**Data type**</span></span> | <span data-ttu-id="ccf85-133">辞書 (入れ子になった基本設定)</span><span class="sxs-lookup"><span data-stu-id="ccf85-133">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="ccf85-134">**コメント**</span><span class="sxs-lookup"><span data-stu-id="ccf85-134">**Comments**</span></span> | <span data-ttu-id="ccf85-135">辞書の内容の説明については、以下のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ccf85-135">See the following sections for a description of the dictionary contents.</span></span> |

<span data-ttu-id="ccf85-136">デバイス制御ポリシーは、次の場合に使用できます。</span><span class="sxs-lookup"><span data-stu-id="ccf85-136">The device control policy can be used to:</span></span>

- [<span data-ttu-id="ccf85-137">デバイス コントロールによって発生する通知の URL ターゲットをカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="ccf85-137">Customize the URL target for notifications raised by device control</span></span>](#customize-url-target-for-notifications-raised-by-device-control)
- [<span data-ttu-id="ccf85-138">リムーバブル デバイスを許可またはブロックする</span><span class="sxs-lookup"><span data-stu-id="ccf85-138">Allow or block removable devices</span></span>](#allow-or-block-removable-devices)

### <a name="customize-url-target-for-notifications-raised-by-device-control"></a><span data-ttu-id="ccf85-139">デバイスコントロールによって発生する通知の URL ターゲットをカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="ccf85-139">Customize URL target for notifications raised by device control</span></span>

<span data-ttu-id="ccf85-140">配置したデバイスコントロール ポリシーがデバイスに適用されている場合 (リムーバブル メディア デバイスへのアクセスが制限されているなど)、ユーザーに通知が表示されます。</span><span class="sxs-lookup"><span data-stu-id="ccf85-140">When the device control policy that you have put in place is enforced on a device (for example, access to a removable media device is restricted), a notification is displayed to the user.</span></span>

![デバイス制御通知](images/mac-device-control-notification.png)

<span data-ttu-id="ccf85-142">エンド ユーザーがこの通知をクリックすると、既定のブラウザーで Web ページが開きます。</span><span class="sxs-lookup"><span data-stu-id="ccf85-142">When end users click this notification, a web page is opened in the default browser.</span></span> <span data-ttu-id="ccf85-143">エンド ユーザーが通知をクリックするときに開く URL を構成できます。</span><span class="sxs-lookup"><span data-stu-id="ccf85-143">You can configure the URL that is opened when end users click the notification.</span></span>

|||
|:---|:---|
| <span data-ttu-id="ccf85-144">**ドメイン**</span><span class="sxs-lookup"><span data-stu-id="ccf85-144">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="ccf85-145">**キー**</span><span class="sxs-lookup"><span data-stu-id="ccf85-145">**Key**</span></span> | <span data-ttu-id="ccf85-146">navigationTarget</span><span class="sxs-lookup"><span data-stu-id="ccf85-146">navigationTarget</span></span> |
| <span data-ttu-id="ccf85-147">**データ型**</span><span class="sxs-lookup"><span data-stu-id="ccf85-147">**Data type**</span></span> | <span data-ttu-id="ccf85-148">文字列</span><span class="sxs-lookup"><span data-stu-id="ccf85-148">String</span></span> |
| <span data-ttu-id="ccf85-149">**コメント**</span><span class="sxs-lookup"><span data-stu-id="ccf85-149">**Comments**</span></span> | <span data-ttu-id="ccf85-150">定義されていない場合、製品は、製品が実行したアクションを説明する汎用ページを指す既定の URL を使用します。</span><span class="sxs-lookup"><span data-stu-id="ccf85-150">If not defined, the product uses a default URL pointing to a generic page explaining the action taken by the product.</span></span> |

### <a name="allow-or-block-removable-devices"></a><span data-ttu-id="ccf85-151">リムーバブル デバイスを許可またはブロックする</span><span class="sxs-lookup"><span data-stu-id="ccf85-151">Allow or block removable devices</span></span>

<span data-ttu-id="ccf85-152">デバイス制御ポリシーのリムーバブル メディア セクションは、リムーバブル メディアへのアクセスを制限するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="ccf85-152">The removable media section of the device control policy is used to restrict access to removable media.</span></span> 

> [!NOTE]
> <span data-ttu-id="ccf85-153">現在サポートされているリムーバブル メディアの種類は次のとおりです。ポリシーには USB ストレージ デバイスを含めできます。</span><span class="sxs-lookup"><span data-stu-id="ccf85-153">The following types of removable media are currently supported and can be included in the policy: USB storage devices.</span></span>

|||
|:---|:---|
| <span data-ttu-id="ccf85-154">**ドメイン**</span><span class="sxs-lookup"><span data-stu-id="ccf85-154">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="ccf85-155">**キー**</span><span class="sxs-lookup"><span data-stu-id="ccf85-155">**Key**</span></span> | <span data-ttu-id="ccf85-156">removableMediaPolicy</span><span class="sxs-lookup"><span data-stu-id="ccf85-156">removableMediaPolicy</span></span> |
| <span data-ttu-id="ccf85-157">**データ型**</span><span class="sxs-lookup"><span data-stu-id="ccf85-157">**Data type**</span></span> | <span data-ttu-id="ccf85-158">辞書 (入れ子になった基本設定)</span><span class="sxs-lookup"><span data-stu-id="ccf85-158">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="ccf85-159">**コメント**</span><span class="sxs-lookup"><span data-stu-id="ccf85-159">**Comments**</span></span> | <span data-ttu-id="ccf85-160">辞書の内容の説明については、以下のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ccf85-160">See the following sections for a description of the dictionary contents.</span></span> |

<span data-ttu-id="ccf85-161">ポリシーのこのセクションは階層構造であり、柔軟性を最大限に高め、幅広い使用例をカバーします。</span><span class="sxs-lookup"><span data-stu-id="ccf85-161">This section of the policy is hierarchical, allowing for maximum flexibility and covering a wide range of use cases.</span></span> <span data-ttu-id="ccf85-162">トップ レベルでは、ベンダー ID によって識別されるベンダーです。</span><span class="sxs-lookup"><span data-stu-id="ccf85-162">At the top level are vendors, identified by a vendor ID.</span></span> <span data-ttu-id="ccf85-163">ベンダーごとに、製品 ID で識別される製品があります。</span><span class="sxs-lookup"><span data-stu-id="ccf85-163">For each vendor, there are products, identified by a product ID.</span></span> <span data-ttu-id="ccf85-164">最後に、製品ごとに、特定のデバイスを示すシリアル番号があります。</span><span class="sxs-lookup"><span data-stu-id="ccf85-164">Finally, for each product there are serial numbers denoting specific devices.</span></span>

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

<span data-ttu-id="ccf85-165">デバイス識別子を検索する方法については、「デバイス識別子を検索 [する」を参照してください](#look-up-device-identifiers)。</span><span class="sxs-lookup"><span data-stu-id="ccf85-165">For information on how to find the device identifiers, see [Look up device identifiers](#look-up-device-identifiers).</span></span>

<span data-ttu-id="ccf85-166">ポリシーは、最も具体的なエントリから最も一般的なエントリに評価されます。</span><span class="sxs-lookup"><span data-stu-id="ccf85-166">The policy is evaluated from the most specific entry to the most general one.</span></span> <span data-ttu-id="ccf85-167">つまり、デバイスが接続されている場合、製品は、各リムーバブル メディア デバイスのポリシーで最も具体的な一致を検索し、そのレベルでアクセス許可を適用します。</span><span class="sxs-lookup"><span data-stu-id="ccf85-167">Meaning, when a device is plugged in, the product tries to find the most specific match in the policy for each removable media device and apply the permissions at that level.</span></span> <span data-ttu-id="ccf85-168">一致しない場合は、デバイスがポリシー内の他のエントリと一致しない場合の既定値である、トップ レベルで指定されたアクセス許可に対して、次の最適な一致が適用されます。</span><span class="sxs-lookup"><span data-stu-id="ccf85-168">If there is no match, then the next best match is applied, all the way to the permission specified at the top level, which is the default when a device does not match any other entry in the policy.</span></span>

#### <a name="policy-enforcement-level"></a><span data-ttu-id="ccf85-169">ポリシーの適用レベル</span><span class="sxs-lookup"><span data-stu-id="ccf85-169">Policy enforcement level</span></span>

<span data-ttu-id="ccf85-170">[リムーバブル メディア] セクションの下には、適用レベルを設定するオプションがあります。このオプションでは、次のいずれかの値を使用できます。</span><span class="sxs-lookup"><span data-stu-id="ccf85-170">Under the removable media section, there is an option to set the enforcement level, which can take one of the following values:</span></span>

- <span data-ttu-id="ccf85-171">`audit` - この適用レベルでは、デバイスへのアクセスが制限されている場合、ユーザーに通知が表示されます。ただし、デバイスは引き続き使用できます。</span><span class="sxs-lookup"><span data-stu-id="ccf85-171">`audit` - Under this enforcement level, if access to a device is restricted, a notification is displayed to the user, however the device can still be used.</span></span> <span data-ttu-id="ccf85-172">この適用レベルは、ポリシーの有効性を評価するために役立ちます。</span><span class="sxs-lookup"><span data-stu-id="ccf85-172">This enforcement level can be useful to evaluate the effectiveness of a policy.</span></span>
- <span data-ttu-id="ccf85-173">`block` - この適用レベルでは、ユーザーがデバイスで実行できる操作は、ポリシーで定義されている操作に制限されます。</span><span class="sxs-lookup"><span data-stu-id="ccf85-173">`block` - Under this enforcement level, the operations that the user can perform on the device are limited to what is defined in the policy.</span></span> <span data-ttu-id="ccf85-174">さらに、ユーザーに通知が発生します。</span><span class="sxs-lookup"><span data-stu-id="ccf85-174">Furthermore, a notification is raised to the user.</span></span> 

|||
|:---|:---|
| <span data-ttu-id="ccf85-175">**ドメイン**</span><span class="sxs-lookup"><span data-stu-id="ccf85-175">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="ccf85-176">**キー**</span><span class="sxs-lookup"><span data-stu-id="ccf85-176">**Key**</span></span> | <span data-ttu-id="ccf85-177">enforcementLevel</span><span class="sxs-lookup"><span data-stu-id="ccf85-177">enforcementLevel</span></span> |
| <span data-ttu-id="ccf85-178">**データ型**</span><span class="sxs-lookup"><span data-stu-id="ccf85-178">**Data type**</span></span> | <span data-ttu-id="ccf85-179">String</span><span class="sxs-lookup"><span data-stu-id="ccf85-179">String</span></span> |
| <span data-ttu-id="ccf85-180">**指定可能な値**</span><span class="sxs-lookup"><span data-stu-id="ccf85-180">**Possible values**</span></span> | <span data-ttu-id="ccf85-181">監査 (既定)</span><span class="sxs-lookup"><span data-stu-id="ccf85-181">audit (default)</span></span> <br/> <span data-ttu-id="ccf85-182">block</span><span class="sxs-lookup"><span data-stu-id="ccf85-182">block</span></span> |

#### <a name="default-permission-level"></a><span data-ttu-id="ccf85-183">既定のアクセス許可レベル</span><span class="sxs-lookup"><span data-stu-id="ccf85-183">Default permission level</span></span>

<span data-ttu-id="ccf85-184">[リムーバブル メディア] セクションのトップ レベルで、ポリシー内の他のアクセス許可と一致しないデバイスの既定のアクセス許可レベルを構成できます。</span><span class="sxs-lookup"><span data-stu-id="ccf85-184">At the top level of the removable media section, you can configure the default permission level for devices that do not match anything else in the policy.</span></span>

<span data-ttu-id="ccf85-185">この設定は、次の値に設定できます。</span><span class="sxs-lookup"><span data-stu-id="ccf85-185">This setting can be set to:</span></span>

- <span data-ttu-id="ccf85-186">`none` - デバイスで操作を実行できません</span><span class="sxs-lookup"><span data-stu-id="ccf85-186">`none` - No operations can be performed on the device</span></span>
- <span data-ttu-id="ccf85-187">次の値の組み合わせ。</span><span class="sxs-lookup"><span data-stu-id="ccf85-187">A combination of the following values:</span></span>
    - <span data-ttu-id="ccf85-188">`read` - デバイスで読み取り操作が許可されている</span><span class="sxs-lookup"><span data-stu-id="ccf85-188">`read` - Read operations are permitted on the device</span></span>
    - <span data-ttu-id="ccf85-189">`write` - デバイスで書き込み操作が許可されている</span><span class="sxs-lookup"><span data-stu-id="ccf85-189">`write` - Write operations are permitted on the device</span></span>
    - <span data-ttu-id="ccf85-190">`execute` - デバイスで実行操作が許可されている</span><span class="sxs-lookup"><span data-stu-id="ccf85-190">`execute` - Execute operations are permitted on the device</span></span>

> [!NOTE]
> <span data-ttu-id="ccf85-191">アクセス `none` 許可レベルに存在する場合、他のアクセス許可 ( `read` 、 、 、 ) `write` `execute` は無視されます。</span><span class="sxs-lookup"><span data-stu-id="ccf85-191">If `none` is present in the permission level, any other permissions (`read`, `write`, or `execute`) will be ignored.</span></span>

> [!NOTE]
> <span data-ttu-id="ccf85-192">この `execute` アクセス許可は、Mach-O バイナリの実行のみを参照します。</span><span class="sxs-lookup"><span data-stu-id="ccf85-192">The `execute` permission only refers to execution of Mach-O binaries.</span></span> <span data-ttu-id="ccf85-193">スクリプトの実行や他の種類のペイロードは含めではありません。</span><span class="sxs-lookup"><span data-stu-id="ccf85-193">It does not include execution of scripts or other types of payloads.</span></span>

|||
|:---|:---|
| <span data-ttu-id="ccf85-194">**ドメイン**</span><span class="sxs-lookup"><span data-stu-id="ccf85-194">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="ccf85-195">**キー**</span><span class="sxs-lookup"><span data-stu-id="ccf85-195">**Key**</span></span> | <span data-ttu-id="ccf85-196">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="ccf85-196">permission</span></span> |
| <span data-ttu-id="ccf85-197">**データ型**</span><span class="sxs-lookup"><span data-stu-id="ccf85-197">**Data type**</span></span> | <span data-ttu-id="ccf85-198">文字列の配列</span><span class="sxs-lookup"><span data-stu-id="ccf85-198">Array of strings</span></span> |
| <span data-ttu-id="ccf85-199">**可能な値**</span><span class="sxs-lookup"><span data-stu-id="ccf85-199">**Possible values**</span></span> | <span data-ttu-id="ccf85-200">none</span><span class="sxs-lookup"><span data-stu-id="ccf85-200">none</span></span> <br/> <span data-ttu-id="ccf85-201">read</span><span class="sxs-lookup"><span data-stu-id="ccf85-201">read</span></span> <br/> <span data-ttu-id="ccf85-202">write</span><span class="sxs-lookup"><span data-stu-id="ccf85-202">write</span></span> <br/> <span data-ttu-id="ccf85-203">execute</span><span class="sxs-lookup"><span data-stu-id="ccf85-203">execute</span></span> |

#### <a name="restrict-removable-media-by-vendor-product-and-serial-number"></a><span data-ttu-id="ccf85-204">ベンダー、製品、シリアル番号によってリムーバブル メディアを制限する</span><span class="sxs-lookup"><span data-stu-id="ccf85-204">Restrict removable media by vendor, product, and serial number</span></span>

<span data-ttu-id="ccf85-205">「リムーバブル デバイス [を許可またはブロック](#allow-or-block-removable-devices)する」で説明したように、USB デバイスなどのリムーバブル メディアは、ベンダー ID、製品 ID、シリアル番号で識別できます。</span><span class="sxs-lookup"><span data-stu-id="ccf85-205">As described in [Allow or block removable devices](#allow-or-block-removable-devices), removable media such as USB devices can be identified by the vendor ID, product ID, and serial number.</span></span>

<span data-ttu-id="ccf85-206">リムーバブル メディア ポリシーのトップ レベルでは、ベンダー レベルで詳細な制限を必要に応じて定義できます。</span><span class="sxs-lookup"><span data-stu-id="ccf85-206">At the top level of the removable media policy, you can optionally define more granular restrictions at the vendor level.</span></span> 

<span data-ttu-id="ccf85-207">ディクショナリ `vendors` には 1 つ以上のエントリが含まれるので、各エントリはベンダー ID で識別されます。</span><span class="sxs-lookup"><span data-stu-id="ccf85-207">The `vendors` dictionary contains one or more entries, with each entry being identified by the vendor ID.</span></span>

|||
|:---|:---|
| <span data-ttu-id="ccf85-208">**ドメイン**</span><span class="sxs-lookup"><span data-stu-id="ccf85-208">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="ccf85-209">**キー**</span><span class="sxs-lookup"><span data-stu-id="ccf85-209">**Key**</span></span> | <span data-ttu-id="ccf85-210">ベンダー</span><span class="sxs-lookup"><span data-stu-id="ccf85-210">vendors</span></span> |
| <span data-ttu-id="ccf85-211">**データ型**</span><span class="sxs-lookup"><span data-stu-id="ccf85-211">**Data type**</span></span> | <span data-ttu-id="ccf85-212">辞書 (入れ子になった基本設定)</span><span class="sxs-lookup"><span data-stu-id="ccf85-212">Dictionary (nested preference)</span></span> |

<span data-ttu-id="ccf85-213">ベンダーごとに、そのベンダーのデバイスに必要なアクセス許可レベルを指定できます。</span><span class="sxs-lookup"><span data-stu-id="ccf85-213">For each vendor, you can specify the desired permission level for devices from that vendor.</span></span>

|||
|:---|:---|
| <span data-ttu-id="ccf85-214">**ドメイン**</span><span class="sxs-lookup"><span data-stu-id="ccf85-214">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="ccf85-215">**キー**</span><span class="sxs-lookup"><span data-stu-id="ccf85-215">**Key**</span></span> | <span data-ttu-id="ccf85-216">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="ccf85-216">permission</span></span> |
| <span data-ttu-id="ccf85-217">**データ型**</span><span class="sxs-lookup"><span data-stu-id="ccf85-217">**Data type**</span></span> | <span data-ttu-id="ccf85-218">文字列の配列</span><span class="sxs-lookup"><span data-stu-id="ccf85-218">Array of strings</span></span> |
| <span data-ttu-id="ccf85-219">**可能な値**</span><span class="sxs-lookup"><span data-stu-id="ccf85-219">**Possible values**</span></span> | <span data-ttu-id="ccf85-220">既定のアクセス [許可レベルと同じ](#default-permission-level)</span><span class="sxs-lookup"><span data-stu-id="ccf85-220">Same as [Default permission level](#default-permission-level)</span></span> |

<span data-ttu-id="ccf85-221">さらに、必要に応じて、より詳細なアクセス許可が定義されているベンダーに属する製品のセットを指定できます。</span><span class="sxs-lookup"><span data-stu-id="ccf85-221">Furthermore, you can optionally specify the set of products belonging to that vendor for which more granular permissions are defined.</span></span> <span data-ttu-id="ccf85-222">ディクショナリ `products` には 1 つ以上のエントリが含まれるので、各エントリは製品 ID で識別されます。</span><span class="sxs-lookup"><span data-stu-id="ccf85-222">The `products` dictionary contains one or more entries, with each entry being identified by the product ID.</span></span> 

|||
|:---|:---|
| <span data-ttu-id="ccf85-223">**ドメイン**</span><span class="sxs-lookup"><span data-stu-id="ccf85-223">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="ccf85-224">**キー**</span><span class="sxs-lookup"><span data-stu-id="ccf85-224">**Key**</span></span> | <span data-ttu-id="ccf85-225">製品</span><span class="sxs-lookup"><span data-stu-id="ccf85-225">products</span></span> |
| <span data-ttu-id="ccf85-226">**データ型**</span><span class="sxs-lookup"><span data-stu-id="ccf85-226">**Data type**</span></span> | <span data-ttu-id="ccf85-227">辞書 (入れ子になった基本設定)</span><span class="sxs-lookup"><span data-stu-id="ccf85-227">Dictionary (nested preference)</span></span> |

<span data-ttu-id="ccf85-228">製品ごとに、その製品の目的のアクセス許可レベルを指定できます。</span><span class="sxs-lookup"><span data-stu-id="ccf85-228">For each product, you can specify the desired permission level for that product.</span></span>

|||
|:---|:---|
| <span data-ttu-id="ccf85-229">**ドメイン**</span><span class="sxs-lookup"><span data-stu-id="ccf85-229">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="ccf85-230">**キー**</span><span class="sxs-lookup"><span data-stu-id="ccf85-230">**Key**</span></span> | <span data-ttu-id="ccf85-231">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="ccf85-231">permission</span></span> |
| <span data-ttu-id="ccf85-232">**データ型**</span><span class="sxs-lookup"><span data-stu-id="ccf85-232">**Data type**</span></span> | <span data-ttu-id="ccf85-233">文字列の配列</span><span class="sxs-lookup"><span data-stu-id="ccf85-233">Array of strings</span></span> |
| <span data-ttu-id="ccf85-234">**可能な値**</span><span class="sxs-lookup"><span data-stu-id="ccf85-234">**Possible values**</span></span> | <span data-ttu-id="ccf85-235">既定のアクセス [許可レベルと同じ](#default-permission-level)</span><span class="sxs-lookup"><span data-stu-id="ccf85-235">Same as [Default permission level](#default-permission-level)</span></span> |

<span data-ttu-id="ccf85-236">さらに、より詳細なアクセス許可が定義されているシリアル番号のオプション セットを指定できます。</span><span class="sxs-lookup"><span data-stu-id="ccf85-236">Furthermore, you can specify an optional set of serial numbers for which more granular permissions are defined.</span></span>

<span data-ttu-id="ccf85-237">辞書 `serialNumbers` には 1 つ以上のエントリが含まれるので、各エントリはシリアル番号で識別されます。</span><span class="sxs-lookup"><span data-stu-id="ccf85-237">The `serialNumbers` dictionary contains one or more entries, with each entry being identified by the serial number.</span></span>

|||
|:---|:---|
| <span data-ttu-id="ccf85-238">**ドメイン**</span><span class="sxs-lookup"><span data-stu-id="ccf85-238">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="ccf85-239">**キー**</span><span class="sxs-lookup"><span data-stu-id="ccf85-239">**Key**</span></span> | <span data-ttu-id="ccf85-240">serialNumbers</span><span class="sxs-lookup"><span data-stu-id="ccf85-240">serialNumbers</span></span> |
| <span data-ttu-id="ccf85-241">**データ型**</span><span class="sxs-lookup"><span data-stu-id="ccf85-241">**Data type**</span></span> | <span data-ttu-id="ccf85-242">辞書 (入れ子になった基本設定)</span><span class="sxs-lookup"><span data-stu-id="ccf85-242">Dictionary (nested preference)</span></span> |

<span data-ttu-id="ccf85-243">シリアル番号ごとに、目的のアクセス許可レベルを指定できます。</span><span class="sxs-lookup"><span data-stu-id="ccf85-243">For each serial number, you can specify the desired permission level.</span></span>

|||
|:---|:---|
| <span data-ttu-id="ccf85-244">**ドメイン**</span><span class="sxs-lookup"><span data-stu-id="ccf85-244">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="ccf85-245">**キー**</span><span class="sxs-lookup"><span data-stu-id="ccf85-245">**Key**</span></span> | <span data-ttu-id="ccf85-246">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="ccf85-246">permission</span></span> |
| <span data-ttu-id="ccf85-247">**データ型**</span><span class="sxs-lookup"><span data-stu-id="ccf85-247">**Data type**</span></span> | <span data-ttu-id="ccf85-248">文字列の配列</span><span class="sxs-lookup"><span data-stu-id="ccf85-248">Array of strings</span></span> |
| <span data-ttu-id="ccf85-249">**可能な値**</span><span class="sxs-lookup"><span data-stu-id="ccf85-249">**Possible values**</span></span> | <span data-ttu-id="ccf85-250">既定のアクセス [許可レベルと同じ](#default-permission-level)</span><span class="sxs-lookup"><span data-stu-id="ccf85-250">Same as [Default permission level](#default-permission-level)</span></span> |

#### <a name="example-device-control-policy"></a><span data-ttu-id="ccf85-251">デバイス制御ポリシーの例</span><span class="sxs-lookup"><span data-stu-id="ccf85-251">Example device control policy</span></span>

<span data-ttu-id="ccf85-252">次の例は、上記のすべての概念をデバイス制御ポリシーに組み合わせる方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="ccf85-252">The following example shows how all of the above concepts can be combined into a device control policy.</span></span> <span data-ttu-id="ccf85-253">次の例では、リムーバブル メディア ポリシーの階層的な性質に注意してください。</span><span class="sxs-lookup"><span data-stu-id="ccf85-253">In the following example, note the hierarchical nature of the removable media policy.</span></span>

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

<span data-ttu-id="ccf85-254">次のドキュメントには、デバイス制御ポリシーのその他の例が含まれています。</span><span class="sxs-lookup"><span data-stu-id="ccf85-254">We have included more examples of device control policies in the following documents:</span></span>

- [<span data-ttu-id="ccf85-255">Intune のデバイス制御ポリシーの例</span><span class="sxs-lookup"><span data-stu-id="ccf85-255">Examples of device control policies for Intune</span></span>](mac-device-control-intune.md)
- [<span data-ttu-id="ccf85-256">JAMF のデバイス制御ポリシーの例</span><span class="sxs-lookup"><span data-stu-id="ccf85-256">Examples of device control policies for JAMF</span></span>](mac-device-control-jamf.md)

#### <a name="look-up-device-identifiers"></a><span data-ttu-id="ccf85-257">デバイス識別子の参照</span><span class="sxs-lookup"><span data-stu-id="ccf85-257">Look up device identifiers</span></span>

<span data-ttu-id="ccf85-258">USB デバイスのベンダー ID、製品 ID、シリアル番号を確認するには、次の方法を実行します。</span><span class="sxs-lookup"><span data-stu-id="ccf85-258">To find the vendor ID, product ID, and serial number of a USB device:</span></span>

1. <span data-ttu-id="ccf85-259">Mac デバイスにログインします。</span><span class="sxs-lookup"><span data-stu-id="ccf85-259">Log into a Mac device.</span></span>
1. <span data-ttu-id="ccf85-260">識別子を参照する USB デバイスを接続します。</span><span class="sxs-lookup"><span data-stu-id="ccf85-260">Plug in the USB device for which you want to look up the identifiers.</span></span>
1. <span data-ttu-id="ccf85-261">macOS のトップ レベル メニューで、[この Mac について **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="ccf85-261">In the top-level menu of macOS, select **About This Mac**.</span></span>

    ![この Mac について](images/mac-device-control-lookup-1.png)

1. <span data-ttu-id="ccf85-263">[システム **レポート] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="ccf85-263">Select **System Report**.</span></span>

    ![システム レポート](images/mac-device-control-lookup-2.png)

1. <span data-ttu-id="ccf85-265">左側の列から **[USB] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="ccf85-265">From the left column, select **USB**.</span></span>

    ![すべての USB デバイスの表示](images/mac-device-control-lookup-3.png)

1. <span data-ttu-id="ccf85-267">[USB **デバイス ツリー]** で、接続した USB デバイスに移動します。</span><span class="sxs-lookup"><span data-stu-id="ccf85-267">Under **USB Device Tree**, navigate to the USB device that you plugged in.</span></span>

    ![USB デバイスの詳細](images/mac-device-control-lookup-4.png)

1. <span data-ttu-id="ccf85-269">ベンダー ID、製品 ID、シリアル番号が表示されます。</span><span class="sxs-lookup"><span data-stu-id="ccf85-269">The vendor ID, product ID, and serial number are displayed.</span></span> <span data-ttu-id="ccf85-270">ベンダー ID と製品 ID をリムーバブル メディア ポリシーに追加する場合は、後にパーツを追加する必要があります `0x` 。</span><span class="sxs-lookup"><span data-stu-id="ccf85-270">When adding the vendor ID and product ID to the removable media policy, you must only add the part after `0x`.</span></span> <span data-ttu-id="ccf85-271">たとえば、次の図では、ベンダー ID は、 `1000` 製品 ID は `090c` です。</span><span class="sxs-lookup"><span data-stu-id="ccf85-271">For example, in the below image, vendor ID is `1000` and product ID is `090c`.</span></span>

#### <a name="discover-usb-devices-in-your-organization"></a><span data-ttu-id="ccf85-272">組織内の USB デバイスを検出する</span><span class="sxs-lookup"><span data-stu-id="ccf85-272">Discover USB devices in your organization</span></span>

<span data-ttu-id="ccf85-273">Microsoft Defender for Endpoint Advanced Hunting で、USB デバイスから発生するマウント、マウント解除、およびボリューム変更イベントを表示できます。</span><span class="sxs-lookup"><span data-stu-id="ccf85-273">You can view mount, unmount, and volume change events originating from USB devices in Microsoft Defender for Endpoint advanced hunting.</span></span> <span data-ttu-id="ccf85-274">これらのイベントは、疑わしい利用状況を特定したり、内部調査を実行したりするのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="ccf85-274">These events can be helpful to identify suspicious usage activity or perform internal investigations.</span></span>

```
DeviceEvents 
    | where ActionType == "UsbDriveMount" or ActionType == "UsbDriveUnmount" or ActionType == "UsbDriveDriveLetterChanged"
    | where DeviceId == "<device ID>"
```

## <a name="device-control-policy-deployment"></a><span data-ttu-id="ccf85-275">デバイス制御ポリシーの展開</span><span class="sxs-lookup"><span data-stu-id="ccf85-275">Device control policy deployment</span></span>

<span data-ttu-id="ccf85-276">「Microsoft Defender for Endpoint for Mac の設定」の説明に従って、デバイス制御ポリシーを他の製品設定の [横に含める必要があります](mac-preferences.md)。</span><span class="sxs-lookup"><span data-stu-id="ccf85-276">The device control policy must be included next to the other product settings, as described in [Set preferences for Microsoft Defender for Endpoint for Mac](mac-preferences.md).</span></span>

<span data-ttu-id="ccf85-277">このプロファイルは、「構成プロファイルの展開」に記載されている手順 [を使用して展開できます](mac-preferences.md#configuration-profile-deployment)。</span><span class="sxs-lookup"><span data-stu-id="ccf85-277">This profile can be deployed using the instructions listed in [Configuration profile deployment](mac-preferences.md#configuration-profile-deployment).</span></span>

## <a name="troubleshooting-tips"></a><span data-ttu-id="ccf85-278">トラブルシューティングのヒント</span><span class="sxs-lookup"><span data-stu-id="ccf85-278">Troubleshooting tips</span></span>

<span data-ttu-id="ccf85-279">Intune または JAMF を介して構成プロファイルをプッシュした後、ターミナルから次のコマンドを実行して、製品によって正常にピックアップされたのか確認できます。</span><span class="sxs-lookup"><span data-stu-id="ccf85-279">After pushing the configuration profile through Intune or JAMF, you can check if it was successfully picked up by the product by running the following command from the Terminal:</span></span>

```bash
mdatp device-control removable-media policy list
```

<span data-ttu-id="ccf85-280">このコマンドは、製品が使用しているデバイス制御ポリシーを標準出力に出力します。</span><span class="sxs-lookup"><span data-stu-id="ccf85-280">This command will print to standard output the device control policy that the product is using.</span></span> <span data-ttu-id="ccf85-281">この印刷を行う場合は、(a) 構成プロファイルが実際に管理コンソールからデバイスにプッシュされ、(b) このドキュメントで説明するように、有効なデバイス制御ポリシーを使用してください。 `Policy is empty`</span><span class="sxs-lookup"><span data-stu-id="ccf85-281">In case this prints `Policy is empty`, make sure that (a) the configuration profile has indeed been pushed to your device from the management console, and (b) it is a valid device control policy, as described in this document.</span></span>

<span data-ttu-id="ccf85-282">ポリシーが正常に配信され、1 つ以上のデバイスが接続されているデバイスで、次のコマンドを実行して、すべてのデバイスと、ポリシーに適用される有効なアクセス許可を一覧表示できます。</span><span class="sxs-lookup"><span data-stu-id="ccf85-282">On a device where the policy has been delivered successfully and where there are one or more devices plugged in, you can run the following command to list all devices and the effective permissions applied to them.</span></span>

```bash
mdatp device-control removable-media devices list
```

<span data-ttu-id="ccf85-283">出力例 :</span><span class="sxs-lookup"><span data-stu-id="ccf85-283">Example of output:</span></span>

```Output
.Device(s)
|-o Name: Untitled 1, Permission ["read", "execute"]
| |-o Vendor: General "fff0"
| |-o Product: USB Flash Disk "1000"
| |-o Serial number: "04ZSSMHI2O7WBVOA"
| |-o Mount point: "/Volumes/TESTUSB"
```

<span data-ttu-id="ccf85-284">上記の例では、デバイスに配信されたデバイス制御ポリシーに従って、接続されているリムーバブル メディア デバイスが 1 つしか接続され、アクセス許可が `read` `execute` 付与されています。</span><span class="sxs-lookup"><span data-stu-id="ccf85-284">In the above example, there is only one removable media device plugged in and it has `read` and `execute` permissions, according to the device control policy that was delivered to the device.</span></span>

## <a name="related-topics"></a><span data-ttu-id="ccf85-285">関連項目</span><span class="sxs-lookup"><span data-stu-id="ccf85-285">Related topics</span></span>

- [<span data-ttu-id="ccf85-286">Intune のデバイス制御ポリシーの例</span><span class="sxs-lookup"><span data-stu-id="ccf85-286">Examples of device control policies for Intune</span></span>](mac-device-control-intune.md)
- [<span data-ttu-id="ccf85-287">JAMF のデバイス制御ポリシーの例</span><span class="sxs-lookup"><span data-stu-id="ccf85-287">Examples of device control policies for JAMF</span></span>](mac-device-control-jamf.md)