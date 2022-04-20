---
title: Microsoft Intuneを使用して macOS デバイスを Microsoft Purview ソリューションにオンボードおよびオフボードする
f1.keywords: NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: Microsoft Intuneを使用して macOS デバイスを Microsoft Purview ソリューションにオンボードおよびオフボードする方法について説明します
ms.openlocfilehash: 99a407b2b0c8d6a506cd138078b3f35cf9e5a232
ms.sourcegitcommit: e911dd506ea066795e418daf7b84c1e11381a21c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/19/2022
ms.locfileid: "64952976"
---
# <a name="onboard-and-offboard-macos-devices-into-microsoft-purview-solutions-using-intune"></a>Intuneを使用して macOS デバイスを Microsoft Purview ソリューションにオンボードおよびオフボードする

[!include[Purview banner](../includes/purview-rebrand-banner.md)]

Intuneを使用して、macOS デバイスを Microsoft Purview ソリューションにオンボードできます。

> [!IMPORTANT]
> macOS デバイスにMicrosoft Defender for Endpoint (MDE) が展開 ***されていない*** 場合は、次の手順を使用します。

**適用対象:**

- [エンドポイントのデータ損失防止](./endpoint-dlp-learn-about.md)
- [インサイダー リスク管理](insider-risk-management.md)

## <a name="before-you-begin"></a>はじめに

- [macOS デバイスがIntuneにオンボード](/mem/intune/fundamentals/deployment-guide-platform-macos)され、[ポータル サイト アプリ](/mem/intune/user-help/enroll-your-device-in-intune-macos-cp)に登録されていることを確認します。 
- [Microsoft エンドポイント マネージャー センター](https://endpoint.microsoft.com/#home)にアクセスできることを確認します。
- これにより、macOS バージョン Catalina 10.15 以降がサポートされます。
- 構成の更新プログラムを割り当てるユーザー グループを作成します。
- macOS デバイスに v95+ Edge ブラウザーをインストールする 


## <a name="onboard-macos-devices-into-microsoft-purview-solutions-using-microsoft-intune"></a>Microsoft Intuneを使用して macOS デバイスを Microsoft Purview ソリューションにオンボードする

macOS デバイスをコンプライアンス ソリューションにオンボードすることは、6 段階のプロセスです。

1. [システム構成プロファイルを作成する](#create-system-configuration-profiles)
1. [デバイスのオンボード パッケージを取得する](#get-the-device-onboarding-package)
1. [オンボード パッケージをデプロイする](#deploy-the-onboarding-package)
1. [システム拡張機能を有効にする](#enable-system-extension)
1. [インストール パッケージを取得する](#get-the-installation-package)
1. [インストール パッケージをデプロイする](#deploy-the-microsoft-dlp-installation-package)

### <a name="create-system-configuration-profiles"></a>システム構成プロファイルを作成する

1. この手順では、これらのファイルが必要です。

|に必要なファイル |source |
|---------|---------|
|オンボード パッケージ    |コンプライアンス ポータルの **オンボード パッケージ** からダウンロードしたファイル名 *DeviceComplianceOnboarding.xml* |
|アクセシビリティ |[accessibility.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/profiles/accessibility.mobileconfig)|
フル ディスク アクセス     |[fulldisk.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/profiles/fulldisk.mobileconfig)|
|ネットワーク ファイルャー| [netfilter.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/profiles/netfilter.mobileconfig)]
|システム拡張機能 |[sysext.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/profiles/sysext.mobileconfig)
|MDE の基本設定     |[com.microsoft.wdav.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/settings/data_loss_prevention/com.microsoft.wdav.mobileconfig)|
|MAU の基本設定|[com.microsoft.autoupdate2.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/settings/microsoft_auto_update/com.microsoft.autoupdate2.mobileconfig)|
|インストール パッケージ     |コンプライアンス ポータルの **インストール パッケージ** からダウンロードしたファイル名 *\*wdav.pkg*\* |

> [!TIP]
> *.mobileconfig* ファイルは、個別にダウンロードすることも、次を含む [単一の結合ファイル](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/combined/mdatp-nokext.mobileconfig)でダウンロードすることもできます。
> - accessibility.mobileconfig
> - fulldisk.mobileconfig
> - netfilter.mobileconfig
> - システム拡張機能
>
>これらの個々のファイルのいずれかが更新された場合は、結合されたファイルを再度ダウンロードするか、1 つの更新されたファイルを個別にダウンロードする必要があります。

<!--2. Copy this code and save it in a file named `com.microsoft.autoupdate2.xml`.

```xml
<?xml version="1.0" encoding="utf-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1">
    <dict>
        <key>PayloadUUID</key>
        <string>B762FF60-6ACB-4A72-9E72-459D00C936F3</string>
        <key>PayloadType</key>
        <string>Configuration</string>
        <key>PayloadOrganization</key>
        <string>Microsoft</string>
        <key>PayloadIdentifier</key>
        <string>com.microsoft.autoupdate2</string>
        <key>PayloadDisplayName</key>
        <string>Microsoft AutoUpdate settings</string>
        <key>PayloadDescription</key>
        <string>Microsoft AutoUpdate configuration settings</string>
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
            <string>5A6F350A-CC2C-440B-A074-68E3F34EBAE9</string>
            <key>PayloadType</key>
            <string>com.microsoft.autoupdate2</string>
            <key>PayloadOrganization</key>
            <string>Microsoft</string>
            <key>PayloadIdentifier</key>
            <string>com.microsoft.autoupdate2</string>
            <key>PayloadDisplayName</key>
            <string>Microsoft AutoUpdate configuration settings</string>
            <key>PayloadDescription</key>
            <string/>
            <key>PayloadVersion</key>
            <integer>1</integer>
            <key>PayloadEnabled</key>
            <true/>
            <key>ChannelName</key>
            <string>Production</string>
            <key>HowToCheck</key>
            <string>AutomaticDownload</string>
            <key>EnableCheckForUpdatesButton</key>
            <true/>
            <key>DisableInsiderCheckbox</key>
            <false/>
            <key>SendAllTelemetryEnabled</key>
            <true/>
            </dict>
        </array>
    </dict>
</plist>
```
-->

2. **Microsoft エンドポイント マネージャー** **centerDevicesConfiguration** >  >  **プロファイルを開きます**。

1. 選択: **プロファイルの作成** 

1. 選択：
    1. **Platform = macOS**
    1. **プロファイルの種類 = テンプレート**
    1. **テンプレート名 = カスタム**

1. [**作成**] を選択する

1. この例の *AccessibilityformacOS* のように、プロファイルの名前を選択します。 [**次へ**]を選択します。

1. 手順 1 でダウンロードした **accessibility.mobileconfig** ファイルを構成プロファイル ファイルとして選択します。

1. **[次へ]** を選択します

1. [ **割り当て** ] タブで、これらの構成を展開するグループを追加し、[ **次へ**] を選択します。

1. 設定を確認し、[ **作成** ] を選択して構成をデプロイします。

1. 手順 3 ~ 11 を繰り返して、次のプロファイルを作成します。
    1. **fulldisk.mobileconfig** ファイル
    1. **com.microsoft.autoupdate2.xml** ファイル
    1. ファイル **com.microsoft.wdav.xml** MDE の基本設定
        1. ウイルス対策エンジン `passive mode` = `true` を設定するか、 `false`. DLP のみを展開する場合に使用します `true`。 DLP とMicrosoft Defender for Endpoint (MDE) を展開する場合は、値を使用`false`するか、割り当てないでください。
    1. **netfilter.mobileconfig**
 
1. **DevicesConfiguration** >  プロファイルを開くと、作成したプロファイルがそこに表示されます。

1. [ **構成プロファイル]** ページで、先ほど作成したプロファイルを選択し、この例の *[アクセシビリティフォームACOS* ] で [ **デバイスの状態** ] を選択して、デバイスの一覧と構成プロファイルの展開状態を表示します。

### <a name="get-the-device-onboarding-package"></a>デバイスのオンボード パッケージを取得する

1. **コンプライアンス センター** で **、設定** > **Device オンボードを** 開き、[**オンボード**] を選択します。
 
1. [ **オペレーティング システムを選択してオンボードプロセスを開始する** ] で **、macOS** を選択します。
 
1. **[展開方法]** で[**モバイル デバイス管理/Microsoft Intune**] を選択します。
 
1. [ **オンボード パッケージのダウンロード**] を選択します。 これには、 *DeviceComplianceOnboarding.xml* ファイルのオンボード コードが含まれます。

### <a name="deploy-the-onboarding-package"></a>オンボード パッケージをデプロイする

1. **Microsoft エンドポイント マネージャー** **centerDevicesConfiguration** >  >  **プロファイルを開きます**。

1. [プロファイル **の作成**] を選択します。 

1. 選択：
    1. **Platform = macOS**
    1. **プロファイルの種類 = テンプレート**
    1. **テンプレート名 = カスタム**

1. [**作成**] を選択する

1. この例の *OnboardingPackage* のように、プロファイルの名前を選択します。 [**次へ**]を選択します。

1. 構成プロファイル ファイルとして *DeviceComplianceOnboarding.xml* ファイルを選択します。

1. **[次へ]** を選択します

1. [ **割り当て** ] タブで、これらの構成を展開するグループを追加し、[ **次へ**] を選択します。

1. 設定を確認し、[ **作成** ] を選択して構成をデプロイします。

### <a name="enable-system-extension"></a>システム拡張機能を有効にする

1. **Microsoft エンドポイント マネージャー センター** で、[構成 **プロファイル] で [プロファイルの作成**] を選択 **します**。

1. 選択：
    1. **Platform = macOS**
    1. **プロファイルの種類 = テンプレート**
    1. **テンプレート名 = 拡張機能**

1. [**作成**] を選択する

1. [ **基本]** タブで、この新しいプロファイルに名前を付けます。

1. [ **構成設定** ] タブで、[ **システム拡張機能] を** 展開します。

1. **[バンドル識別子]** と **[チーム識別子**] で、これらの値を設定します。

|バンドル識別子  |チーム識別子  |
|---------|---------|
|**com.microsoft.wdav.epsext**|**UBF8T346G9**|
|**com.microsoft.wdav.netext**|**UBF8T346G9**|


1. [ **割り当て** ] タブで、これらの構成を展開するグループを追加し、[ **次へ**] を選択します。

1. [ **次へ** ] を選択して構成をデプロイします。

### <a name="get-the-installation-package"></a>インストール パッケージを取得する

1. **コンプライアンス センター** で **、設定** > **Device オンボードを** 開き、[**オンボード**] を選択します。
 
1. オペレーティング **システムを選択してオンボードプロセスを開始するには****、macOS** を選択します
 
1. **[展開方法]** で [**モバイル デバイス管理/Microsoft Intune**] を選択します
 
1. [ **インストール パッケージのダウンロード**] を選択します。 これにより、 *wdav.pkg* ファイルが提供されます。

> [!IMPORTANT]
> *wdav.pkg* をデプロイする前に。 Intuneを使用してパッケージを再フォーマットする必要があります。*Intune App Wrapping Tools for Mac* を使用して *wdav.pkg.intunemac* 形式に再フォーマットする必要があります。
 

### <a name="deploy-the-microsoft-dlp-installation-package"></a>Microsoft DLP インストール パッケージを展開する

1. [「macOS 基幹業務 (LOB) アプリをMicrosoft Intuneに追加する方法」の](/mem/intune/apps/lob-apps-macos)手順に従って *、wdav.pkg* ファイルを適切な形式に変換し、Intuneを使用してデプロイします。

## <a name="offboard-macos-devices-using-intune"></a>Intuneを使用したオフボード macOS デバイス

> [!NOTE]
> オフボードにより、デバイスはポータルへのセンサー データの送信を停止しますが、デバイスからのデータ (発生したアラートへの参照を含む) は、最大 6 か月間保持されます。

2. **Microsoft エンドポイント マネージャー センター** で **DevicesConfiguration** >  プロファイルを開くと、作成したプロファイルがそこに表示されます。

1. [ **構成プロファイル]** ページで、 *wdav.pkg.intunemac* プロファイルを選択します。

1. **デバイスの状態** を選択して、デバイスの一覧と構成プロファイルの展開状態を表示します。

1. **プロパティ** と **割り当てを** 開く

1. 割り当てからグループを削除します。 これにより、 *wdav.pkg.intunemac* パッケージがアンインストールされ、コンプライアンス ソリューションから macOS デバイスがオフボードされます。
