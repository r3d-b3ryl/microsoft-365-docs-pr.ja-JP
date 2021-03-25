---
title: JAMF のデバイス制御ポリシーの例
description: JAMF で使用できる例を使用してデバイス制御ポリシーを使用する方法について説明します。
keywords: microsoft、 defender、 endpoint, atp, mac, device, control, usb, リムーバブル, メディア, jamf
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
ms.openlocfilehash: 8990979024c033d4142b595d6fef94f7b872e7c9
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187684"
---
# <a name="examples-of-device-control-policies-for-jamf"></a><span data-ttu-id="31377-104">JAMF のデバイス制御ポリシーの例</span><span class="sxs-lookup"><span data-stu-id="31377-104">Examples of device control policies for JAMF</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="31377-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="31377-105">**Applies to:**</span></span>
- [<span data-ttu-id="31377-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="31377-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="31377-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="31377-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="31377-108">Microsoft Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="31377-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="31377-109">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="31377-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="31377-110">このドキュメントには、独自の組織用にカスタマイズできるデバイス制御ポリシーの例が記載されています。</span><span class="sxs-lookup"><span data-stu-id="31377-110">This document contains examples of device control policies that you can customize for your own organization.</span></span> <span data-ttu-id="31377-111">これらの例は、JAMF を使用して企業内のデバイスを管理する場合に適用されます。</span><span class="sxs-lookup"><span data-stu-id="31377-111">These examples are applicable if you are using JAMF to manage devices in your enterprise.</span></span>

## <a name="restrict-access-to-all-removable-media"></a><span data-ttu-id="31377-112">すべてのリムーバブル メディアへのアクセスを制限する</span><span class="sxs-lookup"><span data-stu-id="31377-112">Restrict access to all removable media</span></span>

<span data-ttu-id="31377-113">次の例では、すべてのリムーバブル メディアへのアクセスを制限します。</span><span class="sxs-lookup"><span data-stu-id="31377-113">The following example restricts access to all removable media.</span></span> <span data-ttu-id="31377-114">ポリシーのトップ レベルで適用されるアクセス許可に注意してください。つまり、すべてのファイル操作 `none` が禁止されます。</span><span class="sxs-lookup"><span data-stu-id="31377-114">Note the `none` permission that is applied at the top level of the policy, meaning that all file operations will be prohibited.</span></span>

```xml
<?xml version="1.0" encoding="UTF-8"?> 
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd"> 
<plist version="1.0"> 
<dict> 
    <key>deviceControl</key> 
    <dict> 
        <key>removableMediaPolicy</key> 
        <dict> 
            <key>enforcementLevel</key> 
            <string>block</string> 
            <key>permission</key> 
            <array> 
                <string>none</string> 
            </array> 
        </dict> 
    </dict> 
</dict> 
</plist>
```

## <a name="set-all-removable-media-to-be-read-only"></a><span data-ttu-id="31377-115">すべてのリムーバブル メディアを読み取り専用に設定する</span><span class="sxs-lookup"><span data-stu-id="31377-115">Set all removable media to be read-only</span></span>

<span data-ttu-id="31377-116">次の例では、すべてのリムーバブル メディアを読み取り専用に構成します。</span><span class="sxs-lookup"><span data-stu-id="31377-116">The following example configures all removable media to be read-only.</span></span> <span data-ttu-id="31377-117">ポリシーのトップ レベルで適用されるアクセス許可に注意してください。つまり、すべての書き込みおよび実行操作は `read` 許可されません。</span><span class="sxs-lookup"><span data-stu-id="31377-117">Note the `read` permission that is applied at the top level of the policy, meaning that all write and execute operations will be disallowed.</span></span>

```xml
<?xml version="1.0" encoding="UTF-8"?> 
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd"> 
<plist version="1.0"> 
<dict> 
    <key>deviceControl</key> 
    <dict> 
        <key>removableMediaPolicy</key> 
        <dict> 
            <key>enforcementLevel</key> 
            <string>block</string> 
            <key>permission</key> 
            <array> 
                <string>read</string> 
            </array> 
        </dict> 
    </dict> 
</dict> 
</plist>
```

## <a name="disallow-program-execution-from-removable-media"></a><span data-ttu-id="31377-118">リムーバブル メディアからのプログラムの実行を禁止する</span><span class="sxs-lookup"><span data-stu-id="31377-118">Disallow program execution from removable media</span></span>

<span data-ttu-id="31377-119">次の例は、リムーバブル メディアからのプログラムの実行を禁止する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="31377-119">The following example shows how program execution from removable media can be disallowed.</span></span> <span data-ttu-id="31377-120">ポリシーの `read` `write` トップ レベルで適用されるアクセス許可とアクセス許可に注意してください。</span><span class="sxs-lookup"><span data-stu-id="31377-120">Note the `read` and `write` permissions that are applied at the top level of the policy.</span></span>

```xml
<?xml version="1.0" encoding="UTF-8"?> 
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd"> 
<plist version="1.0"> 
<dict> 
    <key>deviceControl</key> 
    <dict> 
        <key>removableMediaPolicy</key> 
        <dict> 
            <key>enforcementLevel</key> 
            <string>block</string> 
            <key>permission</key> 
            <array> 
                <string>read</string>
                <string>write</string> 
            </array> 
        </dict> 
    </dict> 
</dict> 
</plist>
```

## <a name="restrict-all-devices-from-specific-vendors"></a><span data-ttu-id="31377-121">特定のベンダーからすべてのデバイスを制限する</span><span class="sxs-lookup"><span data-stu-id="31377-121">Restrict all devices from specific vendors</span></span>

<span data-ttu-id="31377-122">次の使用例は、特定のベンダーからのすべてのデバイスを制限します (この場合は、and で識別 `fff0` されます `4525` )。</span><span class="sxs-lookup"><span data-stu-id="31377-122">The following example restricts all devices from specific vendors (in this case identified by `fff0` and `4525`).</span></span> <span data-ttu-id="31377-123">ポリシーのトップ レベルで定義されたアクセス許可には、すべての可能なアクセス許可 (読み取り、書き込み、実行) が一覧表示されますので、他のすべてのデバイスは制限されません。</span><span class="sxs-lookup"><span data-stu-id="31377-123">All other devices will be unrestricted, since the permission defined at the top level of the policy lists all possible permissions (read, write, and execute).</span></span>

```xml
<?xml version="1.0" encoding="UTF-8"?> 
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd"> 
<plist version="1.0"> 
<dict> 
    <key>deviceControl</key> 
    <dict> 
        <key>removableMediaPolicy</key> 
        <dict> 
            <key>enforcementLevel</key> 
            <string>block</string> 
            <key>permission</key> 
            <array> 
                <string>read</string>
                <string>write</string>
                <string>execute</string> 
            </array> 
            <key>vendors</key> 
            <dict> 
                <key>fff0</key> 
                <dict> 
                    <key>permission</key> 
                    <array> 
                        <string>none</string> 
                    </array> 
                </dict> 
                <key>4525</key> 
                <dict> 
                    <key>permission</key> 
                    <array>                         
                        <string>none</string> 
                    </array> 
                </dict> 
            </dict> 
        </dict> 
    </dict> 
</dict> 
</plist> 
```

## <a name="restrict-specific-devices-identified-by-vendor-id-product-id-and-serial-number"></a><span data-ttu-id="31377-124">ベンダー ID、製品 ID、シリアル番号で識別される特定のデバイスを制限する</span><span class="sxs-lookup"><span data-stu-id="31377-124">Restrict specific devices identified by vendor ID, product ID, and serial number</span></span>

<span data-ttu-id="31377-125">次の例では、ベンダー ID、製品 ID、シリアル番号で識別される 2 つの特定の `fff0` `1000` デバイスを `04ZSSMHI2O7WBVOA` 制限します `04ZSSMHI2O7WBVOB` 。</span><span class="sxs-lookup"><span data-stu-id="31377-125">The following example restricts two specific devices, identified by vendor ID `fff0`, product ID `1000`, and serial numbers `04ZSSMHI2O7WBVOA` and `04ZSSMHI2O7WBVOB`.</span></span> <span data-ttu-id="31377-126">ポリシーの他のすべてのレベルでは、アクセス許可には、すべての可能な値 (読み取り、書き込み、実行) が含まれます。つまり、他のすべてのデバイスは制限されません。</span><span class="sxs-lookup"><span data-stu-id="31377-126">At all other levels of the policy the permissions include all possible values (read, write, and execute), meaning that all other devices will be unrestricted.</span></span>

```xml
<?xml version="1.0" encoding="UTF-8"?> 
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd"> 
<plist version="1.0"> 
<dict> 
    <key>deviceControl</key> 
    <dict> 
        <key>removableMediaPolicy</key> 
        <dict> 
            <key>enforcementLevel</key> 
            <string>block</string> 
            <key>permission</key> 
            <array> 
                <string>read</string>
                <string>write</string>
                <string>execute</string>
            </array> 
            <key>vendors</key> 
            <dict> 
                <key>fff0</key> 
                <dict> 
                    <key>permission</key> 
                    <array> 
                        <string>read</string> 
                        <string>write</string>
                        <string>execute</string> 
                    </array> 
                    <key>products</key> 
                    <dict> 
                        <key>1000</key> 
                        <dict> 
                            <key>permission</key> 
                            <array> 
                                <string>read</string> 
                                <string>write</string>
                                <string>execute</string>
                            </array> 
                            <key>serialNumbers</key> 
                            <dict> 
                                <key>04ZSSMHI2O7WBVOA</key> 
                                <array> 
                                  <string>none</string> 
                                </array> 
                                <key>04ZSSMHI2O7WBVOB</key>
                                <array> 
                                  <string>none</string> 
                                </array> 
                            </dict> 
                        </dict> 
                    </dict> 
                </dict>
            </dict> 
        </dict> 
    </dict> 
</dict> 
</plist> 
```

## <a name="related-topics"></a><span data-ttu-id="31377-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="31377-127">Related topics</span></span>

- [<span data-ttu-id="31377-128">macOS のデバイス制御の概要</span><span class="sxs-lookup"><span data-stu-id="31377-128">Overview of device control for macOS</span></span>](mac-device-control-overview.md)