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
ms.openlocfilehash: 6f24a610e82388cead88b68e33b76c6404d68ec9
ms.sourcegitcommit: c2d752718aedf958db6b403cc12b972ed1215c00
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58570031"
---
# <a name="device-control-for-macos"></a>macOS のデバイスコントロール

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

## <a name="requirements"></a>要件

macOS のデバイスコントロールには、次の前提条件があります。

>[!div class="checklist"]
> - Microsoft Defender for Endpoint の資格 (試用版の場合があります)
> - 最小 OS バージョン: macOS 11 以上
> - 最小製品バージョン: 101.34.20

## <a name="device-control-policy"></a>デバイス制御ポリシー

macOS のデバイスコントロールを構成するには、組織内で設定する制限を説明するポリシーを作成する必要があります。

デバイス制御ポリシーは、他のすべての製品設定を構成するために使用される構成プロファイルに含まれています。 詳細については、「構成プロファイル [構造」を参照してください](mac-preferences.md#configuration-profile-structure)。

構成プロファイル内で、デバイス制御ポリシーは次のセクションで定義されます。

|Section|値|
|:---|:---|
| **ドメイン** | `com.microsoft.wdav` |
| **Key** | deviceControl |
| **データ型** | 辞書 (入れ子になった基本設定) |
| **コメント** | 辞書の内容の説明については、以下のセクションを参照してください。 |

デバイス制御ポリシーは、次の場合に使用できます。

- [デバイス コントロールによって発生する通知の URL ターゲットをカスタマイズする](#customize-url-target-for-notifications-raised-by-device-control)
- [リムーバブル デバイスを許可またはブロックする](#allow-or-block-removable-devices)

### <a name="customize-url-target-for-notifications-raised-by-device-control"></a>デバイスコントロールによって発生する通知の URL ターゲットをカスタマイズする

配置したデバイスコントロール ポリシーがデバイスに適用されている場合 (リムーバブル メディア デバイスへのアクセスが制限されているなど)、ユーザーに通知が表示されます。

![デバイス制御の通知。](images/mac-device-control-notification.png)

エンド ユーザーがこの通知をクリックすると、既定のブラウザーで Web ページが開きます。 エンド ユーザーが通知をクリックするときに開く URL を構成できます。

|Section|値|
|:---|:---|
| **ドメイン** | `com.microsoft.wdav` |
| **Key** | navigationTarget |
| **データ型** | String |
| **コメント** | 定義されていない場合、製品は、製品が実行したアクションを説明する汎用ページを指す既定の URL を使用します。 |

### <a name="allow-or-block-removable-devices"></a>リムーバブル デバイスを許可またはブロックする

デバイス制御ポリシーのリムーバブル メディア セクションは、リムーバブル メディアへのアクセスを制限するために使用されます。 

> [!NOTE]
> 現在サポートされているリムーバブル メディアの種類は次のとおりです。ポリシーには USB ストレージ デバイスを含めできます。

|Section|値|
|:---|:---|
| **ドメイン** | `com.microsoft.wdav` |
| **Key** | removableMediaPolicy |
| **データ型** | 辞書 (入れ子になった基本設定) |
| **コメント** | 辞書の内容の説明については、以下のセクションを参照してください。 |

ポリシーのこのセクションは階層構造であり、柔軟性を最大限に高め、幅広い使用例をカバーします。 トップ レベルでは、ベンダー ID によって識別されるベンダーです。 ベンダーごとに、製品 ID で識別される製品があります。 最後に、製品ごとに、特定のデバイスを示すシリアル番号があります。

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

デバイス識別子を検索する方法については、「デバイス識別子を検索 [する」を参照してください](#look-up-device-identifiers)。

ポリシーは、最も具体的なエントリから最も一般的なエントリに評価されます。 つまり、デバイスが接続されている場合、製品は、各リムーバブル メディア デバイスのポリシーで最も具体的な一致を検索し、そのレベルでアクセス許可を適用します。 一致しない場合は、デバイスがポリシー内の他のエントリと一致しない場合の既定値である、トップ レベルで指定されたアクセス許可に対して、次の最適な一致が適用されます。

#### <a name="policy-enforcement-level"></a>ポリシーの適用レベル

[リムーバブル メディア] セクションの下には、適用レベルを設定するオプションがあります。このオプションでは、次のいずれかの値を使用できます。

- `audit` - この適用レベルでは、デバイスへのアクセスが制限されている場合、ユーザーに通知が表示されます。ただし、デバイスは引き続き使用できます。 この適用レベルは、ポリシーの有効性を評価するために役立ちます。
- `block` - この適用レベルでは、ユーザーがデバイスで実行できる操作は、ポリシーで定義されている操作に制限されます。 さらに、ユーザーに通知が発生します。 

> [!NOTE] 
> 既定では、適用レベルは に設定されています `audit` 。 

|Section|値|
|:---|:---|
| **ドメイン** | `com.microsoft.wdav` |
| **Key** | enforcementLevel |
| **データ型** | String |
| **指定可能な値** | 監査 (既定) <br/> block |

#### <a name="default-permission-level"></a>既定のアクセス許可レベル

[リムーバブル メディア] セクションのトップ レベルで、ポリシー内の他のアクセス許可と一致しないデバイスの既定のアクセス許可レベルを構成できます。

この設定は、次の値に設定できます。

- `none` - デバイスで操作を実行できません
- 次の値の組み合わせ。
    - `read` - デバイスで読み取り操作が許可されている
    - `write` - デバイスで書き込み操作が許可されている
    - `execute` - デバイスで実行操作が許可されている

> [!NOTE]
> アクセス `none` 許可レベルに存在する場合、他のアクセス許可 ( `read` 、 、 、 ) `write` `execute` は無視されます。

> [!NOTE]
> この `execute` アクセス許可は、Mach-O バイナリの実行のみを参照します。 スクリプトの実行や他の種類のペイロードは含めではありません。

|Section|値|
|:---|:---|
| **ドメイン** | `com.microsoft.wdav` |
| **Key** | アクセス許可 |
| **データ型** | 文字列の配列 |
| **指定可能な値** | none <br/> read <br/> write <br/> execute |

#### <a name="restrict-removable-media-by-vendor-product-and-serial-number"></a>ベンダー、製品、シリアル番号によってリムーバブル メディアを制限する

「リムーバブル デバイス [を許可またはブロック](#allow-or-block-removable-devices)する」で説明したように、USB デバイスなどのリムーバブル メディアは、ベンダー ID、製品 ID、シリアル番号で識別できます。

リムーバブル メディア ポリシーのトップ レベルでは、ベンダー レベルで詳細な制限を必要に応じて定義できます。 

ディクショナリ `vendors` には 1 つ以上のエントリが含まれるので、各エントリはベンダー ID で識別されます。

|Section|値|
|:---|:---|
| **ドメイン** | `com.microsoft.wdav` |
| **Key** | ベンダー |
| **データ型** | 辞書 (入れ子になった基本設定) |

ベンダーごとに、そのベンダーのデバイスに必要なアクセス許可レベルを指定できます。

|Section|値|
|:---|:---|
| **ドメイン** | `com.microsoft.wdav` |
| **Key** | アクセス許可 |
| **データ型** | 文字列の配列 |
| **指定可能な値** | 既定のアクセス [許可レベルと同じ](#default-permission-level) |

さらに、必要に応じて、より詳細なアクセス許可が定義されているベンダーに属する製品のセットを指定できます。 ディクショナリ `products` には 1 つ以上のエントリが含まれるので、各エントリは製品 ID で識別されます。 

|Section|値|
|:---|:---|
| **ドメイン** | `com.microsoft.wdav` |
| **Key** | 製品 |
| **データ型** | 辞書 (入れ子になった基本設定) |

製品ごとに、その製品の目的のアクセス許可レベルを指定できます。

|Section|値|
|:---|:---|
| **ドメイン** | `com.microsoft.wdav` |
| **Key** | アクセス許可 |
| **データ型** | 文字列の配列 |
| **指定可能な値** | 既定のアクセス [許可レベルと同じ](#default-permission-level) |

さらに、より詳細なアクセス許可が定義されているシリアル番号のオプション セットを指定できます。

辞書 `serialNumbers` には 1 つ以上のエントリが含まれるので、各エントリはシリアル番号で識別されます。

|Section|値|
|:---|:---|
| **ドメイン** | `com.microsoft.wdav` |
| **Key** | serialNumbers |
| **データ型** | 辞書 (入れ子になった基本設定) |

シリアル番号ごとに、目的のアクセス許可レベルを指定できます。

|Section|値|
|:---|:---|
| **ドメイン** | `com.microsoft.wdav` |
| **Key** | アクセス許可 |
| **データ型** | 文字列の配列 |
| **指定可能な値** | 既定のアクセス [許可レベルと同じ](#default-permission-level) |

#### <a name="example-device-control-policy"></a>デバイス制御ポリシーの例

次の例は、上記のすべての概念をデバイス制御ポリシーに組み合わせる方法を示しています。 次の例では、リムーバブル メディア ポリシーの階層的な性質に注意してください。

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

次のドキュメントには、デバイス制御ポリシーのその他の例が含まれています。

- [Intune のデバイス制御ポリシーの例](mac-device-control-intune.md)
- [JAMF のデバイス制御ポリシーの例](mac-device-control-jamf.md)

#### <a name="look-up-device-identifiers"></a>デバイス識別子の参照

USB デバイスのベンダー ID、製品 ID、シリアル番号を確認するには、次の方法を実行します。

1. Mac デバイスにログインします。
1. 識別子を参照する USB デバイスを接続します。
1. macOS のトップ レベル メニューで、[この Mac について **] を選択します**。

    ![この Mac について。](images/mac-device-control-lookup-1.png)

1. [システム **レポート] を選択します**。

    ![システム レポート。](images/mac-device-control-lookup-2.png)

1. 左側の列から **[USB] を選択します**。

    ![すべての USB デバイスの表示。](images/mac-device-control-lookup-3.png)

1. [USB **デバイス ツリー]** で、接続した USB デバイスに移動します。

    ![USB デバイスの詳細。](images/mac-device-control-lookup-4.png)

1. ベンダー ID、製品 ID、シリアル番号が表示されます。 ベンダー ID と製品 ID をリムーバブル メディア ポリシーに追加する場合は、後にパーツを追加する必要があります `0x` 。 たとえば、次の図では、ベンダー ID は、 `1000` 製品 ID は `090c` です。

#### <a name="discover-usb-devices-in-your-organization"></a>組織内の USB デバイスを検出する

Microsoft Defender for Endpoint Advanced Hunting で、USB デバイスから発生するマウント、マウント解除、およびボリューム変更イベントを表示できます。 これらのイベントは、疑わしい利用状況を特定したり、内部調査を実行したりするのに役立ちます。

```
DeviceEvents 
    | where ActionType == "UsbDriveMounted" or ActionType == "UsbDriveUnmounted" or ActionType == "UsbDriveDriveLetterChanged"
    | where DeviceId == "<device ID>"
```

## <a name="device-control-policy-deployment"></a>デバイス制御ポリシーの展開

macOS での Microsoft Defender for Endpoint の設定の説明に従って、デバイス制御ポリシーを他の製品設定の横 [に含める必要があります](mac-preferences.md)。

このプロファイルは、「構成プロファイルの展開」に記載されている手順 [を使用して展開できます](mac-preferences.md#configuration-profile-deployment)。

## <a name="troubleshooting-tips"></a>トラブルシューティングのヒント

Intune または JAMF を介して構成プロファイルをプッシュした後、ターミナルから次のコマンドを実行して、製品によって正常にピックアップされたのか確認できます。

```bash
mdatp device-control removable-media policy list
```

このコマンドは、製品が使用しているデバイス制御ポリシーを標準出力に出力します。 この印刷を行う場合は、(a) 構成プロファイルが実際に管理コンソールからデバイスにプッシュされ、(b) このドキュメントで説明するように、有効なデバイス制御ポリシーを使用してください。 `Policy is empty`

ポリシーが正常に配信され、1 つ以上のデバイスが接続されているデバイスで、次のコマンドを実行して、すべてのデバイスと、ポリシーに適用される有効なアクセス許可を一覧表示できます。

```bash
mdatp device-control removable-media devices list
```

出力例 :

```Output
.Device(s)
|-o Name: Untitled 1, Permission ["read", "execute"]
| |-o Vendor: General "fff0"
| |-o Product: USB Flash Disk "1000"
| |-o Serial number: "04ZSSMHI2O7WBVOA"
| |-o Mount point: "/Volumes/TESTUSB"
```

上記の例では、デバイスに配信されたデバイス制御ポリシーに従って、接続されているリムーバブル メディア デバイスが 1 つしか接続され、アクセス許可が `read` `execute` 付与されています。

## <a name="related-topics"></a>関連項目

- [Intune のデバイス制御ポリシーの例](mac-device-control-intune.md)
- [JAMF のデバイス制御ポリシーの例](mac-device-control-jamf.md)
