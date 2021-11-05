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
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: MDE のお客様向けソリューションを使用して、Microsoft 365コンプライアンス ソリューションに macOS デバイスMicrosoft Intuneオンボードおよびオフボードする方法 (プレビュー)
ms.openlocfilehash: 94664f0d57f1b702484e27c62f9e80339e04e105
ms.sourcegitcommit: bf3965b46487f6f8cf900dd9a3af8b213a405989
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/03/2021
ms.locfileid: "60701315"
---
# <a name="onboard-and-offboard-macos-devices-into-compliance-solutions-using-intune-for-microsoft-defender-for-endpoint-customers-preview"></a>Microsoft Defender for Endpoint のお客様向け Intune を使用したコンプライアンス ソリューションへのオンボードおよびオフボード macOS デバイス (プレビュー)

> [!IMPORTANT]
> Microsoft Defender  for Endpoint (MDE) を macOS デバイスに展開している場合は、次の手順を実行します。

## <a name="get-registered"></a>登録を取得する

この機能にアクセスするには、テナントを Microsoft に登録する必要があります。 macOS[のサポートに登録Microsoft 365を参照してください](https://aka.ms/Ignite2021DLP)。

**適用対象:**

- MDE を macOS デバイスに展開しているお客様。
- [Microsoft 365エンドポイント データ損失防止 (DLP)](./endpoint-dlp-learn-about.md)
- [インサイダー リスクの管理](insider-risk-management.md#learn-about-insider-risk-management-in-microsoft-365)


## <a name="before-you-begin"></a>はじめに

- macOS デバイス[が Intune](/mem/intune/fundamentals/deployment-guide-platform-macos)にオンボードされ、アプリに登録ポータル サイト[します](/mem/intune/user-help/enroll-your-device-in-intune-macos-cp)。 
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
> *.mobileconfig* ファイルは、個別にダウンロードするか、以下を含 [む単一の結合ファイル](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/combined/mdatp-nokext.mobileconfig)でダウンロードできます。
> - アクセシビリティ.mobileconfig
> - fulldisk.mobileconfig
> 
>
>これらの個々のファイルが更新された場合は、結合されたファイルを再度ダウンロードするか、単一の更新されたファイルを個別にダウンロードする必要があります。

### <a name="create-system-configuration-profiles"></a>システム構成プロファイルの作成

1. デバイス構成 **プロファイルMicrosoft エンドポイント マネージャー**  >  **センター**  >  **を開きます**。

1. [プロファイルの **作成] を選択します**。 

1. 次のオプションを選択します。
    1. **プラットフォーム = macOS**
    1. **プロファイルの種類 = テンプレート**
    1. **テンプレート名 = カスタム**

1. [作成 **] を選択します。**

1. この例のアクセシビリティフォーム *acOS* など、プロファイルの名前を選択します。 [**次へ**]を選択します。

1. 手順 1 **でダウンロードしたアクセシビリティ.mobileconfig** ファイルを構成プロファイル ファイルとして選択します。

1. [次へ **] を選択する**

1. [割り **当て]** タブで、これらの構成を展開するグループを追加し、[次へ] を **選択します**。

1. 設定を確認し、[作成] **を選択して** 構成を展開します。

1. デバイス **構成**  >  **プロファイルを開きます**。作成したプロファイルが表示されます。

1. [構成プロファイル **]** ページで、作成したプロファイルを次の例の *AccessibilityformacOS* で選択し、[デバイスの状態] を選択して、デバイスの一覧と構成プロファイルの展開状態を表示します。

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

1. **[Microsoft エンドポイント マネージャーで、[****デバイス** 構成プロファイル] を開きます。作成した  >  プロファイルが表示されます。

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
3. **保存 .**