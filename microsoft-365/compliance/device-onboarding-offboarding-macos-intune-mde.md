---
title: Microsoft Defender for Endpoint のお客様向けMicrosoft Intuneコンプライアンス ソリューションへのオンボードおよびオフボード macOS デバイス (プレビュー)
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
description: MDE のお客様向けソリューションを使用して、Microsoft 365コンプライアンス ソリューションに macOS Microsoft Intuneオンボードおよびオフボードする方法について (プレビュー)
ms.openlocfilehash: 6cc4362e924f291c6a8396bff342c6f628e33be3
ms.sourcegitcommit: 3fb76db6b34e24569417f4c8a41b99f46a780389
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/17/2022
ms.locfileid: "63526556"
---
# <a name="onboard-and-offboard-macos-devices-into-compliance-solutions-using-intune-for-microsoft-defender-for-endpoint-customers-preview"></a>Microsoft Defender for Endpoint のお客様向け Intune を使用したコンプライアンス ソリューションへの macOS デバイスのオンボードとオフボード (プレビュー)

> [!IMPORTANT]
> Microsoft Defender for  Endpoint (MDE) を macOS デバイスに展開している場合は、次の手順を実行します。

**適用対象:**

- MDE を macOS デバイスに展開しているお客様。
- [Microsoft 365 エンドポイントのデータ損失防止 (DLP)](./endpoint-dlp-learn-about.md)
- [インサイダー リスク管理](insider-risk-management.md#learn-about-insider-risk-management-in-microsoft-365)


## <a name="before-you-begin"></a>はじめに

- macOS デバイス[が Intune に](/mem/intune/fundamentals/deployment-guide-platform-macos)オンボードされ、アプリに登録ポータル サイト[します](/mem/intune/user-help/enroll-your-device-in-intune-macos-cp)。 
- サーバー センターにアクセス[Microsoft エンドポイント マネージャーする](https://endpoint.microsoft.com/#home)
- これは macOS バージョン Catalina 10.15 以上をサポートしています
- macOS デバイスに v95+ Edge ブラウザーをインストールする 

## <a name="onboard-macos-devices-into-microsoft-365-compliance-solutions-using-microsoft-intune"></a>macOS デバイスを、Microsoft 365を使用してコンプライアンス ソリューションにオンボードMicrosoft Intune

MDE が既に展開されている場合は、以下の手順を使用して macOS デバイスをコンプライアンス ソリューションにオンボードします。

1. この手順では、これらのファイルが必要です。

|に必要なファイル |source |
|---------|---------|
|アクセシビリティ |[アクセシビリティ.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/profiles/accessibility.mobileconfig)|
フル ディスク アクセス     |[fulldisk.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/profiles/fulldisk.mobileconfig)|

> [!TIP]
> *.mobileconfig ファイルは*、個別にダウンロードするか、以下を含 [む単一の結合ファイル](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/combined/mdatp-nokext.mobileconfig)でダウンロードできます。
> - アクセシビリティ.mobileconfig
> - fulldisk.mobileconfig
> 
>
>これらの個々のファイルが更新された場合は、結合されたファイルを再度ダウンロードするか、単一の更新されたファイルを個別にダウンロードする必要があります。

### <a name="create-system-configuration-profiles"></a>システム構成プロファイルの作成

1. **centerDevicesConfiguration** >  **プロファイルMicrosoft エンドポイント マネージャー** > 開 **きます**。

1. [プロファイルの **作成] を選択します**。 

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

1. **DevicesConfiguration** >  **プロファイルを開** きます。作成したプロファイルが表示されます。

1. [構成プロファイル **]** ページで、作成したプロファイルを次の *例の AccessibilityformacOS* で選択し、[デバイスの状態] を選択して、デバイスの一覧と構成プロファイルの展開状態を表示します。

### <a name="update-configuration-profiles"></a>構成プロファイルの更新

1. **fulldisk.mobileconfig** ファイルを使用して、既存のフル ディスク アクセス プロファイルを更新します。

1. これらの値を使用して MDE 基本設定プロファイルを更新する
   
```xml
<key>features</key>
<dict>
    <key>systemExtensions</key>
    <string>enabled</string>
    <key>dataLossPrevention</key>
    <string>enabled</string>
</dict>
```

## <a name="offboard-macos-devices-using-intune"></a>Intune を使用したオフボード macOS デバイス

> [!IMPORTANT]
> Offboarding を使用すると、デバイスはポータルへのセンサー データの送信を停止しますが、デバイスからのデータ (通知への参照を含む) は最大 6 か月間保持されます。

1. 中央 **Microsoft エンドポイント マネージャー** **DevicesConfiguration** >  プロファイルを開きます。作成したプロファイルがそこに表示されます。

2. [構成 **プロファイル] ページで** 、MDE 基本設定プロファイルを選択します。

1. 次の設定を削除します。
   
```xml
<key>features</key>
<dict>
    <key>systemExtensions</key>
    <string>enabled</string>
    <key>dataLossPrevention</key>
    <string>enabled</string>
</dict>
```
3. **保存します**。