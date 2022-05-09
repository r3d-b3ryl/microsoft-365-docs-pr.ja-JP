---
title: macOS のデバイス制御
description: USB デバイスなどのリムーバブル ストレージからの脅威を軽減するために Mac でMicrosoft Defender for Endpointを構成する方法について説明します。
keywords: microsoft, defender, Microsoft Defender for Endpoint, mac, デバイス, コントロール, USB, リムーバブル, メディア
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
ms.openlocfilehash: fbe693272a2f2893dff5f8614f3f9eff301069fd
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2022
ms.locfileid: "64477305"
---
# <a name="device-control-for-macos"></a>macOS のデバイス制御

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

## <a name="requirements"></a>要件

macOS のデバイス制御には、次の前提条件があります。

> [!div class="checklist"]
>
> - Microsoft Defender for Endpoint資格 (試用可能)
> - 最小 OS バージョン: macOS 11 以降
> - 製品の最小バージョン: 101.34.20

## <a name="device-control-policy"></a>デバイス制御ポリシー

macOS のデバイス制御を構成するには、組織内で設定する制限を説明するポリシーを作成する必要があります。

デバイス制御ポリシーは、他のすべての製品設定の構成に使用される構成プロファイルに含まれます。 詳細については、「 [構成プロファイル構造」を](mac-preferences.md#configuration-profile-structure)参照してください。

構成プロファイル内で、デバイス制御ポリシーは次のセクションで定義されます。

<br>

****

|Section|値|
|---|---|
|**ドメイン**|`com.microsoft.wdav`|
|**キー**|deviceControl|
|**データ型**|ディクショナリ (入れ子になった設定)|
|**Comments**|ディクショナリの内容の説明については、次のセクションを参照してください。|
|

デバイス制御ポリシーは、次の場合に使用できます。

- [デバイス コントロールによって発生する通知の URL ターゲットをカスタマイズする](#customize-url-target-for-notifications-raised-by-device-control)
- [リムーバブル デバイスを許可またはブロックする](#allow-or-block-removable-devices)

### <a name="customize-url-target-for-notifications-raised-by-device-control"></a>デバイス制御によって発生する通知の URL ターゲットをカスタマイズする

配置したデバイス制御ポリシーがデバイスに適用されると (リムーバブル メディア デバイスへのアクセスが制限されているなど)、ユーザーに通知が表示されます。

:::image type="content" source="images/mac-device-control-notification.png" alt-text="デバイスコントロールの通知" lightbox="images/mac-device-control-notification.png":::

エンド ユーザーがこの通知をクリックすると、Web ページが既定のブラウザーで開きます。 エンド ユーザーが通知をクリックしたときに開く URL を構成できます。

<br>

****

|Section|値|
|---|---|
|**ドメイン**|`com.microsoft.wdav`|
|**キー**|navigationTarget|
|**データ型**|String|
|**コメント**|定義されていない場合、製品は、製品によって実行されたアクションを説明する汎用ページを指す既定の URL を使用します。|
|

### <a name="allow-or-block-removable-devices"></a>リムーバブル デバイスを許可またはブロックする

デバイス制御ポリシーのリムーバブル メディア セクションは、リムーバブル メディアへのアクセスを制限するために使用されます。

> [!NOTE]
> 現在、次の種類のリムーバブル メディアがサポートされており、ポリシーに含めることができます:USB ストレージ デバイス。

<br>

****

|Section|値|
|---|---|
|**ドメイン**|`com.microsoft.wdav`|
|**キー**|removableMediaPolicy|
|**データ型**|ディクショナリ (入れ子になった設定)|
|**Comments**|ディクショナリの内容の説明については、次のセクションを参照してください。|
|

ポリシーのこのセクションは階層型であり、柔軟性を最大限に高め、幅広いユース ケースをカバーします。 最上位レベルはベンダーであり、ベンダー ID で識別されます。 ベンダーごとに、製品 ID で識別される製品があります。 最後に、製品ごとに、特定のデバイスを示すシリアル番号があります。

```text
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

デバイス識別子を検索する方法については、「デバイス識別子を [検索する](#look-up-device-identifiers)」を参照してください。

ポリシーは、最も具体的なエントリから最も一般的なものまで評価されます。 つまり、デバイスが接続されると、製品はリムーバブル メディア デバイスごとにポリシー内で最も具体的な一致を見つけ、そのレベルでアクセス許可を適用しようとします。 一致するものがない場合は、次に最適な一致が適用され、最上位レベルで指定されたアクセス許可まですべて適用されます。これは、デバイスがポリシー内の他のエントリと一致しない場合の既定値です。

#### <a name="policy-enforcement-level"></a>ポリシーの適用レベル

[リムーバブル メディア] セクションには、適用レベルを設定するオプションがあります。これには、次のいずれかの値を使用できます。

- `audit` - この適用レベルでは、デバイスへのアクセスが制限されている場合は、通知がユーザーに表示されます。ただし、デバイスは引き続き使用できます。 この適用レベルは、ポリシーの有効性を評価するのに役立ちます。
- `block` - この適用レベルでは、ユーザーがデバイスで実行できる操作は、ポリシーで定義されている操作に制限されます。 さらに、通知がユーザーに送信されます。

> [!NOTE]
> 既定では、適用レベルは `audit`.

<br>

****

|Section|値|
|---|---|
|**ドメイン**|`com.microsoft.wdav`|
|**キー**|enforcementLevel|
|**データ型**|String|
|**指定可能な値**|監査 (既定) <p> ブロック|
|

#### <a name="default-permission-level"></a>既定のアクセス許可レベル

リムーバブル メディア セクションの最上位レベルでは、ポリシー内の他のデバイスと一致しないデバイスの既定のアクセス許可レベルを構成できます。

この設定は次のように設定できます。

- `none` - デバイスで操作を実行できない
- 次の値の組み合わせ。
  - `read` - デバイスで読み取り操作が許可される
  - `write` - デバイスで書き込み操作が許可される
  - `execute` - デバイスで実行操作が許可される

> [!NOTE]
> アクセス許可レベルに存在する場合`none`、その他のアクセス許可 (`read`または `execute``write`) は無視されます。
>
> アクセス許可は `execute` 、Mach-O バイナリの実行のみを参照します。 スクリプトや他の種類のペイロードの実行は含まれません。

<br>

****

|Section|値|
|---|---|
|**ドメイン**|`com.microsoft.wdav`|
|**キー**|アクセス 許可|
|**データ型**|文字列の配列|
|**指定可能な値**|none <p> read <p> write <p> 実行|
|

#### <a name="restrict-removable-media-by-vendor-product-and-serial-number"></a>ベンダー、製品、シリアル番号によってリムーバブル メディアを制限する

リムーバブル デバイスの [許可またはブロック](#allow-or-block-removable-devices)に関する説明に従って、USB デバイスなどのリムーバブル メディアは、ベンダー ID、製品 ID、シリアル番号で識別できます。

リムーバブル メディア ポリシーの最上位レベルでは、必要に応じてベンダー レベルで、より詳細な制限を定義できます。

ディクショナリには `vendors` 1 つ以上のエントリが含まれています。各エントリはベンダー ID で識別されます。

<br>

****

|Section|値|
|---|---|
|**ドメイン**|`com.microsoft.wdav`|
|**キー**|ベンダー|
|**データ型**|ディクショナリ (入れ子になった設定)|
|

ベンダーごとに、そのベンダーのデバイスに必要なアクセス許可レベルを指定できます。

<br>

****

|Section|値|
|---|---|
|**ドメイン**|`com.microsoft.wdav`|
|**キー**|アクセス 許可|
|**データ型**|文字列の配列|
|**指定可能な値**|[既定のアクセス許可レベル](#default-permission-level)と同じ|
|

さらに、必要に応じて、より詳細なアクセス許可が定義されているそのベンダーに属する製品のセットを指定できます。 `products`ディクショナリには 1 つ以上のエントリが含まれています。各エントリは製品 ID で識別されます。

<br>

****

|Section|値|
|---|---|
|**ドメイン**|`com.microsoft.wdav`|
|**キー**|製品|
|**データ型**|ディクショナリ (入れ子になった設定)|
|

製品ごとに、その製品に必要なアクセス許可レベルを指定できます。

<br>

****

|Section|値|
|---|---|
|**ドメイン**|`com.microsoft.wdav`|
|**キー**|アクセス 許可|
|**データ型**|文字列の配列|
|**指定可能な値**|[既定のアクセス許可レベル](#default-permission-level)と同じ|
|

さらに、より詳細なアクセス許可が定義されているシリアル番号のオプション セットを指定することもできます。

ディクショナリには `serialNumbers` 1 つ以上のエントリが含まれています。各エントリはシリアル番号で識別されます。

<br>

****

|Section|値|
|---|---|
|**ドメイン**|`com.microsoft.wdav`|
|**キー**|serialNumbers|
|**データ型**|ディクショナリ (入れ子になった設定)|
|

シリアル番号ごとに、必要なアクセス許可レベルを指定できます。

<br>

****

|Section|値|
|---|---|
|**ドメイン**|`com.microsoft.wdav`|
|**キー**|アクセス 許可|
|**データ型**|文字列の配列|
|**指定可能な値**|[既定のアクセス許可レベル](#default-permission-level)と同じ|
|

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

デバイス制御ポリシーの例を次のドキュメントに追加しました。

- [Intuneのデバイス制御ポリシーの例](mac-device-control-intune.md)
- [JAMF のデバイス制御ポリシーの例](mac-device-control-jamf.md)

#### <a name="look-up-device-identifiers"></a>デバイス識別子を検索する

USB デバイスのベンダー ID、製品 ID、シリアル番号を確認するには、

1. Mac デバイスにログインします。
1. 識別子を検索する USB デバイスを接続します。
1. macOS の最上位メニューで、[ **この Mac について**] を選択します。

   :::image type="content" source="images/mac-device-control-lookup-1.png" alt-text="[この Mac について] ページ" lightbox="images/mac-device-control-lookup-1.png":::

1. **[システム レポート] を選択します**。

   :::image type="content" source="images/mac-device-control-lookup-2.png" alt-text="システム レポート" lightbox="images/mac-device-control-lookup-2.png":::

1. 左側の列から **USB** を選択します。

   :::image type="content" source="images/mac-device-control-lookup-3.png" alt-text="すべての USB デバイスのビュー" lightbox="images/mac-device-control-lookup-3.png":::
    

1. [ **USB デバイス ツリー]** で、接続した USB デバイスに移動します。

   :::image type="content" source="images/mac-device-control-lookup-4.png" alt-text="USB デバイスの詳細" lightbox="images/mac-device-control-lookup-4.png":::

1. ベンダー ID、製品 ID、シリアル番号が表示されます。 リムーバブル メディア ポリシーにベンダー ID と製品 ID を追加する場合は、次の部分 `0x`のみを追加する必要があります。 たとえば、次の図では、ベンダー ID と `1000` 製品 ID は `090c`.

#### <a name="discover-usb-devices-in-your-organization"></a>組織内の USB デバイスを検出する

高度なハンティングで USB デバイスから発生したマウント、マウント解除、およびボリューム変更イベントMicrosoft Defender for Endpoint表示できます。 これらのイベントは、疑わしい使用状況を特定したり、内部調査を実行したりするのに役立ちます。

```bash
DeviceEvents
    | where ActionType == "UsbDriveMounted" or ActionType == "UsbDriveUnmounted" or ActionType == "UsbDriveDriveLetterChanged"
    | where DeviceId == "<device ID>"
```

## <a name="device-control-policy-deployment"></a>デバイス制御ポリシーの展開

[macOS でのMicrosoft Defender for Endpointの設定](mac-preferences.md)の説明に従って、デバイス制御ポリシーを他の製品設定の横に含める必要があります。

このプロファイルは、「構成プロファイルの展開」に記載されている手順を使用して [デプロイ](mac-preferences.md#configuration-profile-deployment)できます。

## <a name="troubleshooting-tips"></a>トラブルシューティングのヒント

Intuneまたは JAMF を介して構成プロファイルをプッシュした後、ターミナルから次のコマンドを実行して、製品によって正常に取得されたかどうかを確認できます。

```bash
mdatp device-control removable-media policy list
```

このコマンドは、製品が使用しているデバイス制御ポリシーを標準出力に出力します。 この印刷を行 `Policy is empty`う場合は、(a) 構成プロファイルが実際に管理コンソールからデバイスにプッシュされていることを確認し、(b) このドキュメントで説明されているように、有効なデバイス制御ポリシーであることを確認します。

ポリシーが正常に配信され、1 つ以上のデバイスが接続されているデバイスで、次のコマンドを実行して、すべてのデバイスと、それらに適用された有効なアクセス許可を一覧表示できます。

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

上の例では、デバイスに配信されたデバイス制御ポリシーに従って `read` 、リムーバブル メディア デバイスが 1 つだけ接続されており、アクセス許可と `execute` アクセス許可があります。

## <a name="related-topics"></a>関連項目

- [Intuneのデバイス制御ポリシーの例](mac-device-control-intune.md)
- [JAMF のデバイス制御ポリシーの例](mac-device-control-jamf.md)
