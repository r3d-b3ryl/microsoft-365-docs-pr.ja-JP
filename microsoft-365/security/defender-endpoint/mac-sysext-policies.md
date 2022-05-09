---
title: macOS Catalina および macOS の新しいバージョンの新しい構成プロファイル
description: このトピックでは、macOS Catalina および新しいバージョンの macOS のカーネル拡張機能の代わりに使用されるシステム拡張機能のメリットを得るために行う必要がある変更について説明します。
keywords: microsoft, defender, Microsoft Defender for Endpoint, mac, カーネル, システム, 拡張機能, catalina
search.product: eADQiWindows 10XVcnh
search.appverid: met150
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
ROBOTS: noindex,nofollow
ms.technology: mde
ms.openlocfilehash: 53194aac16091b9afd9559b4f372c2d436c198bf
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2022
ms.locfileid: "64474709"
---
# <a name="new-configuration-profiles-for-macos-catalina-and-newer-versions-of-macos"></a>macOS Catalina および macOS の新しいバージョンの新しい構成プロファイル

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

macOS の進化に合わせて、カーネル拡張機能の代わりにシステム拡張機能を利用する macOS 更新プログラムのMicrosoft Defender for Endpointを準備しています。 この更新プログラムは、macOS Catalina (10.15.4) 以降のバージョンの macOS にのみ適用されます。

マネージド環境 (JAMF、Intune、または別の MDM ソリューション経由) で macOS にMicrosoft Defender for Endpointをデプロイした場合は、新しい構成プロファイルをデプロイする必要があります。 これらの手順を実行しないと、ユーザーはこれらの新しいコンポーネントを実行するための承認プロンプトを受け取ります。

## <a name="jamf"></a>JAMF

### <a name="jamf-system-extensions-policy"></a>JAMF システム拡張機能ポリシー

システム拡張機能を承認するには、次のペイロードを作成します。

1. **[コンピューター>構成プロファイル**] で、[**オプション] > [システム拡張機能**] を選択します。
2. [ **システム拡張機能** の種類] ドロップダウン リストから [許可された **システム拡張機能** ] を選択します。
3. チーム ID には **UBF8T346G9** を使用します。
4. **許可されたシステム拡張機能** の一覧に次のバンドル識別子を追加します。

    - **com.microsoft.wdav.epsext**
    - **com.microsoft.wdav.netext**

    :::image type="content" source="images/mac-approved-system-extensions.png" alt-text=" [承認済みシステム拡張機能] ページ" lightbox="images/mac-approved-system-extensions.png":::

### <a name="privacy-preferences-policy-control"></a>プライバシー設定ポリシーコントロール

次の JAMF ペイロードを追加して、Microsoft Defender for Endpoint エンドポイント セキュリティ拡張機能へのフル ディスク アクセスを許可します。 このポリシーは、デバイスで拡張機能を実行するための前提条件です。

1. **[オプション** \> **のプライバシー設定] ポリシー コントロールを** 選択します。
2. **識別子**`Bundle ID`と **バンドルの種類** として使用`com.microsoft.wdav.epsext`します。
3. コード要件を次に設定する `identifier "com.microsoft.wdav.epsext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`
4. **アプリまたはサービス** を **SystemPolicyAllFiles** に設定し、**アクセスを許可** に設定します。

   :::image type="content" source="images/mac-system-extension-privacy.png" alt-text=" [プライバシー設定ポリシー コントロール] メニュー項目" lightbox="images/mac-system-extension-privacy.png":::

### <a name="network-extension-policy"></a>ネットワーク拡張ポリシー

エンドポイントの検出と応答機能の一環として、macOS のMicrosoft Defender for Endpointはソケット トラフィックを検査し、この情報をMicrosoft 365 Defender ポータルに報告します。 次のポリシーを使用すると、ネットワーク拡張機能でこの機能を実行できます。

> [!NOTE]
> JAMF にはコンテンツ フィルター ポリシーのサポートが組み込まれていません。これは、macOS にMicrosoft Defender for Endpointネットワーク拡張機能をデバイスにインストールするための前提条件です。 さらに、JAMF によって、デプロイされるポリシーの内容が変更されることがあります。
> そのため、次の手順では、構成プロファイルへの署名を含む回避策を提供します。

1. テキスト エディターを使用して、次の `com.microsoft.network-extension.mobileconfig` コンテンツをデバイスに保存します。

    ```xml
    <?xml version="1.0" encoding="UTF-8"?><!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
    <plist version="1">
        <dict>
            <key>PayloadUUID</key>
            <string>DA2CC794-488B-4AFF-89F7-6686A7E7B8AB</string>
            <key>PayloadType</key>
            <string>Configuration</string>
            <key>PayloadOrganization</key>
            <string>Microsoft Corporation</string>
            <key>PayloadIdentifier</key>
            <string>DA2CC794-488B-4AFF-89F7-6686A7E7B8AB</string>
            <key>PayloadDisplayName</key>
            <string>Microsoft Defender Network Extension</string>
            <key>PayloadDescription</key>
            <string/>
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
                    <string>2BA070D9-2233-4827-AFC1-1F44C8C8E527</string>
                    <key>PayloadType</key>
                    <string>com.apple.webcontent-filter</string>
                    <key>PayloadOrganization</key>
                    <string>Microsoft Corporation</string>
                    <key>PayloadIdentifier</key>
                    <string>CEBF7A71-D9A1-48BD-8CCF-BD9D18EC155A</string>
                    <key>PayloadDisplayName</key>
                    <string>Approved Network Extension</string>
                    <key>PayloadDescription</key>
                    <string/>
                    <key>PayloadVersion</key>
                    <integer>1</integer>
                    <key>PayloadEnabled</key>
                    <true/>
                    <key>FilterType</key>
                    <string>Plugin</string>
                    <key>UserDefinedName</key>
                    <string>Microsoft Defender Network Extension</string>
                    <key>PluginBundleID</key>
                    <string>com.microsoft.wdav</string>
                    <key>FilterSockets</key>
                    <true/>
                    <key>FilterDataProviderBundleIdentifier</key>
                    <string>com.microsoft.wdav.netext</string>
                    <key>FilterDataProviderDesignatedRequirement</key>
                    <string>identifier "com.microsoft.wdav.netext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9</string>
                </dict>
            </array>
        </dict>
    </plist>
    ```

2. ターミナルでユーティリティを実行して、上記のファイルが `plutil` 正しくコピーされたことを確認します。

    ```bash
    $ plutil -lint <PathToFile>/com.microsoft.network-extension.mobileconfig
    ```

    たとえば、ファイルがドキュメントに格納されている場合は次のようになります。

    ```bash
    $ plutil -lint ~/Documents/com.microsoft.network-extension.mobileconfig
    ```

    コマンドが出力されることを確認します `OK`。

    ```bash
    <PathToFile>/com.microsoft.network-extension.mobileconfig: OK
    ```

3. [このページ](https://www.jamf.com/jamf-nation/articles/649/creating-a-signing-certificate-using-jamf-pro-s-built-in-certificate-authority)の指示に従って、JAMF の組み込みの証明機関を使用して署名証明書を作成します。

4. 証明書を作成してデバイスにインストールしたら、ターミナルから次のコマンドを実行してファイルに署名します。

    ```bash
    $ security cms -S -N "<CertificateName>" -i <PathToFile>/com.microsoft.network-extension.mobileconfig -o <PathToSignedFile>/com.microsoft.network-extension.signed.mobileconfig
    ```

    たとえば、証明書名が **SigningCertificate** で、署名されたファイルがドキュメントに格納される場合は次のようになります。

    ```bash
    $ security cms -S -N "SigningCertificate" -i ~/Documents/com.microsoft.network-extension.mobileconfig -o ~/Documents/com.microsoft.network-extension.signed.mobileconfig
    ```

5. JAMF ポータルで、[**構成プロファイル]** に移動し、[**アップロード**] ボタンをクリックします。 ファイルの入力を求められたら選択 `com.microsoft.network-extension.signed.mobileconfig` します。

## <a name="intune"></a>Intune

### <a name="intune-system-extensions-policy"></a>Intune システム拡張機能ポリシー

システム拡張機能を承認するには:

1. Intuneで、[**デバイス構成** の **管理**\>] を開きます。 [**プロファイルの****管理**\>] **の [プロファイル** の\>作成] を選択します。
2. プロファイルの名前を選択します。 **Platform=macOS** を **プロファイルの種類=拡張機能** に変更します。 **[作成]** を選択します。
3. タブで `Basics` 、この新しいプロファイルに名前を付けます。
4. タブで `Configuration settings` 、セクションに次のエントリを `Allowed system extensions` 追加します。

   <br>

   ****

   |バンドル識別子|チーム識別子|
   |---|---|
   |com.microsoft.wdav.epsext|UBF8T346G9|
   |com.microsoft.wdav.netext|UBF8T346G9|
   |||

   :::image type="content" source="images/mac-system-extension-intune2.png" alt-text=" [システム構成プロファイル] ページ" lightbox="images/mac-system-extension-intune2.png":::

5. タブで `Assignments` 、このプロファイルを **[すべてのユーザー] & [すべてのデバイス**] に割り当てます。
6. この構成プロファイルを確認して作成します。

### <a name="create-and-deploy-the-custom-configuration-profile"></a>カスタム構成プロファイルを作成してデプロイする

次の構成プロファイルは、ネットワーク拡張機能を有効にし、Endpoint Security システム拡張機能へのフル ディスク アクセスを許可します。

次のコンテンツをsysext.xmlという名前 **の** ファイルに保存します。

```xml
<?xml version="1.0" encoding="UTF-8"?><!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1">
    <dict>
        <key>PayloadUUID</key>
        <string>7E53AC50-B88D-4132-99B6-29F7974EAA3C</string>
        <key>PayloadType</key>
        <string>Configuration</string>
        <key>PayloadOrganization</key>
        <string>Microsoft Corporation</string>
        <key>PayloadIdentifier</key>
        <string>7E53AC50-B88D-4132-99B6-29F7974EAA3C</string>
        <key>PayloadDisplayName</key>
        <string>Microsoft Defender System Extensions</string>
        <key>PayloadDescription</key>
        <string/>
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
                <string>2BA070D9-2233-4827-AFC1-1F44C8C8E527</string>
                <key>PayloadType</key>
                <string>com.apple.webcontent-filter</string>
                <key>PayloadOrganization</key>
                <string>Microsoft Corporation</string>
                <key>PayloadIdentifier</key>
                <string>CEBF7A71-D9A1-48BD-8CCF-BD9D18EC155A</string>
                <key>PayloadDisplayName</key>
                <string>Approved Network Extension</string>
                <key>PayloadDescription</key>
                <string/>
                <key>PayloadVersion</key>
                <integer>1</integer>
                <key>PayloadEnabled</key>
                <true/>
                <key>FilterType</key>
                <string>Plugin</string>
                <key>UserDefinedName</key>
                <string>Microsoft Defender Network Extension</string>
                <key>PluginBundleID</key>
                <string>com.microsoft.wdav</string>
                <key>FilterSockets</key>
                <true/>
                <key>FilterDataProviderBundleIdentifier</key>
                <string>com.microsoft.wdav.netext</string>
                <key>FilterDataProviderDesignatedRequirement</key>
                <string>identifier &quot;com.microsoft.wdav.netext&quot; and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9</string>
            </dict>
            <dict>
                <key>PayloadUUID</key>
                <string>56105E89-C7C8-4A95-AEE6-E11B8BEA0366</string>
                <key>PayloadType</key>
                <string>com.apple.TCC.configuration-profile-policy</string>
                <key>PayloadOrganization</key>
                <string>Microsoft Corporation</string>
                <key>PayloadIdentifier</key>
                <string>56105E89-C7C8-4A95-AEE6-E11B8BEA0366</string>
                <key>PayloadDisplayName</key>
                <string>Privacy Preferences Policy Control</string>
                <key>PayloadDescription</key>
                <string/>
                <key>PayloadVersion</key>
                <integer>1</integer>
                <key>PayloadEnabled</key>
                <true/>
                <key>Services</key>
                <dict>
                    <key>SystemPolicyAllFiles</key>
                    <array>
                        <dict>
                            <key>Identifier</key>
                            <string>com.microsoft.wdav.epsext</string>
                            <key>CodeRequirement</key>
                            <string>identifier "com.microsoft.wdav.epsext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9</string>
                            <key>IdentifierType</key>
                            <string>bundleID</string>
                            <key>StaticCode</key>
                            <integer>0</integer>
                            <key>Allowed</key>
                            <integer>1</integer>
                        </dict>
                    </array>
                </dict>
            </dict>
        </array>
    </dict>
</plist>
```

上記のファイルが正しくコピーされたことを確認します。 ターミナルから次のコマンドを実行し、出力 `OK`されることを確認します。

```bash
$ plutil -lint sysext.xml
sysext.xml: OK
```

このカスタム構成プロファイルをデプロイするには、

1. Intuneで、[**デバイス構成** の **管理**\>] を開きます。 [**プロファイルの****管理**\>] プロファイルの\>作成を選択 **します**。
2. プロファイルの名前を選択します。 **Platform=macOS** と **プロファイルの種類=カスタム** を変更します。 **[構成]** を選択します。
3. 構成プロファイルを開き、 **sysext.xml** アップロードします。 このファイルは、前の手順で作成されました。
4. **[OK]** を選択します。

   :::image type="content" source="images/mac-system-extension-intune.png" alt-text="[Intune] ページの [システム拡張機能]" lightbox="images/mac-system-extension-intune.png":::

5. タブで `Assignments` 、このプロファイルを **[すべてのユーザー] & [すべてのデバイス**] に割り当てます。
6. この構成プロファイルを確認して作成します。
