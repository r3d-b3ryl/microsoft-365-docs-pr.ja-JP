---
title: オンボードおよびオフボードの macOS デバイスMicrosoft 365コンプライアンス ソリューションへのMicrosoft Intune (プレビュー)
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
description: macOS デバイスをオンボーディングおよびオフボードで、Microsoft 365コンプライアンス ソリューションにMicrosoft Intuneする方法 (プレビュー)
ms.openlocfilehash: 5f8dd27490992e15d53dfc10311ce7b23b99683a
ms.sourcegitcommit: 3fb76db6b34e24569417f4c8a41b99f46a780389
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/17/2022
ms.locfileid: "63526514"
---
# <a name="onboard-and-offboard-macos-devices-into-microsoft-365-compliance-solutions-using-intune-preview"></a>Intune を使用した Microsoft 365 コンプライアンス ソリューションへの macOS デバイスのオンボードとオフボード (プレビュー)

Intune を使用して、コンプライアンス ソリューションに macOS デバイスMicrosoft 365できます。

> [!IMPORTANT]
> MacOS デバイスに Microsoft  Defender for Endpoint (MDE) が展開されていない場合は、次の手順を実行します。

**適用対象:**

- [Microsoft 365 エンドポイントのデータ損失防止 (DLP)](./endpoint-dlp-learn-about.md)
- [インサイダー リスク管理](insider-risk-management.md#learn-about-insider-risk-management-in-microsoft-365)

## <a name="before-you-begin"></a>はじめに

- macOS デバイス[が Intune に](/mem/intune/fundamentals/deployment-guide-platform-macos)オンボードされ、アプリに登録ポータル サイト[します](/mem/intune/user-help/enroll-your-device-in-intune-macos-cp)。 
- サーバー センターにアクセスMicrosoft エンドポイント マネージャー[します](https://endpoint.microsoft.com/#home)。
- これは macOS バージョン Catalina 10.15 以上をサポートします。
- 構成更新プログラムを割り当てるユーザー グループを作成します。
- macOS デバイスに v95+ Edge ブラウザーをインストールする 


## <a name="onboard-macos-devices-into-microsoft-365-compliance-solutions-using-microsoft-intune"></a>macOS デバイスを、Microsoft 365を使用してコンプライアンス ソリューションにオンボードMicrosoft Intune

コンプライアンス ソリューションへの macOS デバイスのオンボードは、6 段階のプロセスです。

1. [システム構成プロファイルの作成](#create-system-configuration-profiles)
1. [デバイスオンボーディング パッケージの取得](#get-the-device-onboarding-package)
1. [オンボーディング パッケージの展開](#deploy-the-onboarding-package)
1. [システム拡張機能を有効にする](#enable-system-extension)
1. [インストール パッケージの取得](#get-the-installation-package)
1. [インストール パッケージの展開](#deploy-the-microsoft-dlp-installation-package)

### <a name="create-system-configuration-profiles"></a>システム構成プロファイルの作成

1. この手順では、これらのファイルが必要です。

|に必要なファイル |source |
|---------|---------|
|オンボーディング パッケージ    |コンプライアンス ポータルのオンボード パッケージ **からダウンロードされたファイル***名DeviceComplianceOnboarding.xml* |
|アクセシビリティ |[アクセシビリティ.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/profiles/accessibility.mobileconfig)|
フル ディスク アクセス     |[fulldisk.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/profiles/fulldisk.mobileconfig)|
|ネットワーク ファイル| [netfilter.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/profiles/netfilter.mobileconfig)]
|システム拡張機能 |[sysext.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/profiles/sysext.mobileconfig)
|MDE の基本設定     |[com.microsoft.wdav.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/settings/data_loss_prevention/com.microsoft.wdav.mobileconfig)|
|MAU の基本設定|[com.microsoft.autoupdate2.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/settings/microsoft_auto_update/com.microsoft.autoupdate2.mobileconfig)|
|インストール パッケージ     |コンプライアンス ポータルのインストール パッケージ **からダウンロードされたファイル** 名 *\*wdav.pkg*\* |

> [!TIP]
> *.mobileconfig ファイルは*、個別にダウンロードするか、以下を含 [む単一の結合ファイル](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/combined/mdatp-nokext.mobileconfig)でダウンロードできます。
> - アクセシビリティ.mobileconfig
> - fulldisk.mobileconfig
> - netfilter.mobileconfig
> - システム拡張機能
>
>これらの個々のファイルが更新された場合は、結合されたファイルを再度ダウンロードするか、単一の更新されたファイルを個別にダウンロードする必要があります。

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

2. **centerDevicesConfiguration** >  **プロファイルMicrosoft エンドポイント マネージャー** > 開 **きます**。

1. 選択: **プロファイルの作成** 

1. 次のオプションを選択します。
    1. **プラットフォーム = macOS**
    1. **プロファイルの種類 = テンプレート**
    1. **テンプレート名 = カスタム**

1. [作成 **] を選択します。**

1. この例のアクセシビリティフォーム *acOS* など、プロファイルの名前を選択します。 **次へ** を選択します。

1. 手順 1 **でダウンロードしたアクセシビリティ.mobileconfig** ファイルを構成プロファイル ファイルとして選択します。

1. **[次へ]** を選択します

1. [割り **当て]** タブで、これらの構成を展開するグループを追加し、[次へ] を選択 **します**。

1. 設定を確認し、[作成] **を選択して** 構成を展開します。

1. 手順 3 ~ 11 を繰り返して、次のプロファイルを作成します。
    1. **fulldisk.mobileconfig** ファイル
    1. **com.microsoft.autoupdate2.xml** ファイル
    1. MDE 基本設定 **com.microsoft.wdav.xml** ファイル
        1. ウイルス対策エンジンまたは`passive mode` = `true`を設定します。`false` DLP `true`のみを展開する場合に使用します。 DLP `false` と Microsoft Defender for Endpoint (MDE) を展開する場合は、値を使用するか、割り当てない。
    1. **netfilter.mobileconfig**
 
1. **DevicesConfiguration** >  **プロファイルを開** きます。作成したプロファイルが表示されます。

1. [構成プロファイル **]** ページで、作成したプロファイルを次の *例の AccessibilityformacOS* で選択し、[デバイスの状態] を選択して、デバイスの一覧と構成プロファイルの展開状態を表示します。

### <a name="get-the-device-onboarding-package"></a>デバイスオンボーディング パッケージの取得

1. [**コンプライアンス センター] で [****設定** > **Device オン** ボーディング] を開き、[オンボーディング] **を選択します**。
 
1. [**オンボーディング プロセスを開始するオペレーティング システムの選択] で、****macOS を選択します**。
 
1. [**展開方法] で**、[**モバイル デバイスの管理/管理] をMicrosoft Intune**。
 
1. [オンボード **パッケージのダウンロード] を選択します**。 これには、データベース ファイル内のオンボーディング *DeviceComplianceOnboarding.xml* 含まれる。

### <a name="deploy-the-onboarding-package"></a>オンボーディング パッケージの展開

1. **centerDevicesConfiguration** >  **プロファイルMicrosoft エンドポイント マネージャー** > 開 **きます**。

1. [プロファイルの **作成] を選択します**。 

1. 次のオプションを選択します。
    1. **プラットフォーム = macOS**
    1. **プロファイルの種類 = テンプレート**
    1. **テンプレート名 = カスタム**

1. [作成 **] を選択します。**

1. この例の *OnboardingPackage など、プロファイルの名前* を選択します。 **次へ** を選択します。

1. 構成プロファイル *ファイルDeviceComplianceOnboarding.xml* ファイルを選択します。

1. **[次へ]** を選択します

1. [割り **当て]** タブで、これらの構成を展開するグループを追加し、[次へ] を選択 **します**。

1. 設定を確認し、[作成] **を選択して** 構成を展開します。

### <a name="enable-system-extension"></a>システム拡張機能を有効にする

1. [構成プロファイル **] Microsoft エンドポイント マネージャー[****プロファイルの作成] を** 選択 **します。**

1. 次のオプションを選択します。
    1. **プラットフォーム = macOS**
    1. **プロファイルの種類 = テンプレート**
    1. **テンプレート名 = 拡張機能**

1. [作成 **] を選択します。**

1. [基本 **] タブで** 、この新しいプロファイルに名前を付きます。

1. [構成設定 **] タブで** 、[ **システム拡張機能] を展開します**。

1. [**バンドル識別子と****チーム識別子] で**、これらの値を設定します。

|バンドル識別子  |チーム識別子  |
|---------|---------|
|**com.microsoft.wdav.epsext**|**UBF8T346G9**|
|**com.microsoft.wdav.netext**|**UBF8T346G9**|


1. [割り **当て]** タブで、これらの構成を展開するグループを追加し、[次へ] を選択 **します**。

1. [ **次へ] を** 選択して構成を展開します。

### <a name="get-the-installation-package"></a>インストール パッケージの取得

1. [**コンプライアンス センター] で [****設定** > **Device オン** ボーディング] を開き、[オンボーディング] **を選択します**。
 
1. [ **オンボーディング プロセスを開始するオペレーティング システムの選択] で** **macOS を選択する**
 
1. [**展開方法] で** [**モバイル デバイスの管理/管理] を選択Microsoft Intune**
 
1. [インストール **パッケージのダウンロード] を選択します**。 これにより、 *wdav.pkg ファイルが表示* されます。

> [!IMPORTANT]
> *wdav.pkg を展開する前に。* パッケージを Intune 経由で使用する場合は、 *Intune アプリ ラッピング ツール for Mac* を使用して *wdav.pkg.intunemac 形式に再フォーマットする必要* があります。
 

### <a name="deploy-the-microsoft-dlp-installation-package"></a>Microsoft DLP インストール パッケージの展開

1. [「macOS line-of-business (LOB)](/mem/intune/apps/lob-apps-macos) アプリを Microsoft Intune に追加する方法」の手順に従って、*wdav.pkg* ファイルを適切な形式に変換し、Intune を介して展開します。

## <a name="offboard-macos-devices-using-intune"></a>Intune を使用したオフボード macOS デバイス

> [!NOTE]
> Offboarding を使用すると、デバイスはポータルへのセンサー データの送信を停止しますが、デバイスからのデータ (通知への参照を含む) は、最大 6 か月間保持されます。

2. 中央 **Microsoft エンドポイント マネージャー** **DevicesConfiguration** >  プロファイルを開きます。作成したプロファイルがそこに表示されます。

1. [構成 **プロファイル] ページで** 、 *wdav.pkg.intunemac プロファイルを選択* します。

1. [ **デバイスの状態]** を選択して、デバイスの一覧と構成プロファイルの展開状態を表示します。

1. プロパティ **と割り****当てを開く**

1. 割り当てからグループを削除します。 これにより、 *wdav.pkg.intunemac* パッケージがアンインストールされ、コンプライアンス ソリューションから macOS デバイスのオフボードがアンインストールされます。
