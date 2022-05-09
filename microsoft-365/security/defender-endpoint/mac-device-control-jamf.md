---
title: JAMF のデバイス制御ポリシーの例
description: JAMF で使用できる例を使用して、デバイス制御ポリシーを使用する方法について説明します。
keywords: microsoft, defender, エンドポイント, Microsoft Defender for Endpoint, mac, デバイス, コントロール, USB, リムーバブル, メディア, jamf
ms.prod: m365-security
ms.mktglfcycl: security
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 74925625f6d004c1901756cde75310b345dd5747
ms.sourcegitcommit: 6e90baef421ae06fd790b0453d3bdbf624b7f9c0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/12/2022
ms.locfileid: "62766034"
---
# <a name="examples-of-device-control-policies-for-jamf"></a>JAMF のデバイス制御ポリシーの例

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

このドキュメントには、独自の組織用にカスタマイズできるデバイス制御ポリシーの例が含まれています。 これらの例は、JAMF を使用して企業内のデバイスを管理する場合に適用されます。

## <a name="restrict-access-to-all-removable-media"></a>すべてのリムーバブル メディアへのアクセスを制限する

次の例では、すべてのリムーバブル メディアへのアクセスを制限します。 ポリシーの `none` 最上位レベルで適用されるアクセス許可に注意してください。つまり、すべてのファイル操作が禁止されます。

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

## <a name="set-all-removable-media-to-be-read-only"></a>すべてのリムーバブル メディアを読み取り専用に設定する

次の例では、すべてのリムーバブル メディアを読み取り専用に構成します。 ポリシーの `read` 最上位レベルで適用されるアクセス許可に注意してください。つまり、すべての書き込み操作と実行操作は許可されません。

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

## <a name="disallow-program-execution-from-removable-media"></a>リムーバブル メディアからプログラムの実行を禁止する

次の例は、リムーバブル メディアからのプログラムの実行を禁止する方法を示しています。 ポリシーの `read` 最上位レベルで適用されるアクセス許可と `write` アクセス許可に注意してください。

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

## <a name="restrict-all-devices-from-specific-vendors"></a>特定のベンダーからのすべてのデバイスを制限する

次の例では、特定のベンダーからのすべてのデバイスを制限します (この場合は、特定され `fff0` 、 `4525`特定されます)。 ポリシーの最上位レベルで定義されているアクセス許可には、使用可能なすべてのアクセス許可 (読み取り、書き込み、実行) が一覧表示されるため、他のすべてのデバイスは制限されません。

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

## <a name="restrict-specific-devices-identified-by-vendor-id-product-id-and-serial-number"></a>ベンダー ID、製品 ID、シリアル番号で識別される特定のデバイスを制限する

次の例では、ベンダー ID、製品 ID`fff0``1000`、シリアル番号`04ZSSMHI2O7WBVOA``04ZSSMHI2O7WBVOB`、および . ポリシーの他のすべてのレベルでは、アクセス許可に可能なすべての値 (読み取り、書き込み、実行) が含まれています。つまり、他のすべてのデバイスは制限されません。

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

## <a name="related-topics"></a>関連項目

- [macOS のデバイス制御の概要](mac-device-control-overview.md)
