---
title: Intune のデバイス制御ポリシーの例
description: Intune で使用できる例を使用してデバイス制御ポリシーを使用する方法について説明します。
keywords: microsoft、 defender、 Microsoft Defender for Endpoint, mac, device, control, usb, リムーバブル, メディア, intune
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
ms.openlocfilehash: e9edec2b4e0b08cf6506f6234fbfb1f2c3c03914
ms.sourcegitcommit: 6e90baef421ae06fd790b0453d3bdbf624b7f9c0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/12/2022
ms.locfileid: "62767102"
---
# <a name="examples-of-device-control-policies-for-intune"></a>Intune のデバイス制御ポリシーの例

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

このドキュメントには、独自の組織用にカスタマイズできるデバイス制御ポリシーの例が記載されています。 これらの例は、Intune を使用して企業内のデバイスを管理する場合に適用されます。

## <a name="restrict-access-to-all-removable-media"></a>すべてのリムーバブル メディアへのアクセスを制限する

次の例では、すべてのリムーバブル メディアへのアクセスを制限します。 ポリシーの `none` トップ レベルで適用されるアクセス許可に注意してください。つまり、すべてのファイル操作が許可されません。

```xml
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
        <string>Microsoft Defender settings</string>
        <key>PayloadDescription</key>
        <string>Microsoft Defender configuration settings</string>
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
                <string>Microsoft Defender configuration settings</string>
                <key>PayloadDescription</key>
                <string/>
                <key>PayloadVersion</key>
                <integer>1</integer>
                <key>PayloadEnabled</key>
                <true/>
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
        </array>
    </dict>
</plist>
```

## <a name="set-all-removable-media-to-be-read-only"></a>すべてのリムーバブル メディアを読み取り専用に設定する

次の例では、すべてのリムーバブル メディアを読み取り専用に構成します。 ポリシーの `read` トップ レベルで適用されるアクセス許可に注意してください。つまり、すべての書き込みおよび実行操作は許可されません。

```xml
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
        <string>Microsoft Defender settings</string>
        <key>PayloadDescription</key>
        <string>Microsoft Defender configuration settings</string>
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
                <string>Microsoft Defender configuration settings</string>
                <key>PayloadDescription</key>
                <string/>
                <key>PayloadVersion</key>
                <integer>1</integer>
                <key>PayloadEnabled</key>
                <true/>
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
        </array>
    </dict>
</plist>
```

## <a name="disallow-program-execution-from-removable-media"></a>リムーバブル メディアからのプログラムの実行を禁止する

次の例は、リムーバブル メディアからのプログラムの実行を禁止する方法を示しています。 ポリシーの `read` トップ `write` レベルで適用されるアクセス許可とアクセス許可に注意してください。

```xml
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
        <string>Microsoft Defender settings</string>
        <key>PayloadDescription</key>
        <string>Microsoft Defender configuration settings</string>
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
                <string>Microsoft Defender configuration settings</string>
                <key>PayloadDescription</key>
                <string/>
                <key>PayloadVersion</key>
                <integer>1</integer>
                <key>PayloadEnabled</key>
                <true/>
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
        </array>
    </dict>
</plist>
```

## <a name="restrict-all-devices-from-specific-vendors"></a>特定のベンダーからすべてのデバイスを制限する

次の使用例は、特定のベンダーからのすべてのデバイスを制限します (この場合は、and で識別 `fff0` されます `4525`)。 ポリシーのトップ レベルで定義されたアクセス許可には、すべての可能なアクセス許可 (読み取り、書き込み、実行) が一覧表示されますので、他のすべてのデバイスは制限されません。

```xml
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
        <string>Microsoft Defender settings</string>
        <key>PayloadDescription</key>
        <string>Microsoft Defender configuration settings</string>
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
                <string>Microsoft Defender configuration settings</string>
                <key>PayloadDescription</key>
                <string/>
                <key>PayloadVersion</key>
                <integer>1</integer>
                <key>PayloadEnabled</key>
                <true/>
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
        </array>
    </dict>
</plist>
```

## <a name="restrict-specific-devices-identified-by-vendor-id-product-id-and-serial-number"></a>ベンダー ID、製品 ID、シリアル番号で識別される特定のデバイスを制限する

次の例では、ベンダー ID、製品 ID`fff0``1000`、シリアル番号で識別される 2 つの特定のデバイスを制限`04ZSSMHI2O7WBVOA`します`04ZSSMHI2O7WBVOB`。 ポリシーの他のすべてのレベルでは、アクセス許可には、すべての可能な値 (読み取り、書き込み、実行) が含まれます。つまり、他のすべてのデバイスは制限されません。

```xml
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
        <string>Microsoft Defender settings</string>
        <key>PayloadDescription</key>
        <string>Microsoft Defender configuration settings</string>
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
                <string>Microsoft Defender configuration settings</string>
                <key>PayloadDescription</key>
                <string/>
                <key>PayloadVersion</key>
                <integer>1</integer>
                <key>PayloadEnabled</key>
                <true/>
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
        </array>
    </dict>
</plist>
```

## <a name="related-topics"></a>関連項目

- [macOS のデバイス制御の概要](mac-device-control-overview.md)
