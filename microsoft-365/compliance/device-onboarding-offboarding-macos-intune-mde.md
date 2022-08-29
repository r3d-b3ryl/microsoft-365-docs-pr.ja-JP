---
title: Microsoft Defender for Endpoint顧客向けのMicrosoft Intuneを使用して、macOS デバイスをコンプライアンス ソリューションにオンボードおよびオフボードする
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
description: MDE のお客様向けのMicrosoft Intuneを使用して、macOS デバイスを Microsoft Purview ソリューションにオンボードおよびオフボードする方法について説明します
ms.openlocfilehash: b14b8c8385bd1a67265b36006c35d35612a32e3c
ms.sourcegitcommit: d09eb780dc41a01796eb8137fbe9267231af6746
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/19/2022
ms.locfileid: "67385509"
---
# <a name="onboard-and-offboard-macos-devices-into-compliance-solutions-using-intune-for-microsoft-defender-for-endpoint-customers"></a>Microsoft Defender for Endpoint のお客様向け Intune を使用したコンプライアンス ソリューションへの macOS デバイスのオンボードとオフボード

> [!IMPORTANT]
> macOS デバイスに Microsoft Defender for Endpoint (MDE) を展開している ***場合は***、次の手順を使用します。

**適用対象:**

- MACOS デバイスに MDE を展開しているお客様。
- [エンドポイントのデータ損失防止](./endpoint-dlp-learn-about.md)
- [インサイダー リスク管理](insider-risk-management.md)


## <a name="before-you-begin"></a>はじめに

- [macOS デバイスがIntuneにオンボードされ](/mem/intune/fundamentals/deployment-guide-platform-macos)、[ポータル サイト アプリ](/mem/intune/user-help/enroll-your-device-in-intune-macos-cp)に登録されていることを確認します。 
- [Microsoft エンドポイント マネージャー センター](https://endpoint.microsoft.com/#home)にアクセスできることを確認する
- これにより、macOS バージョン Catalina 10.15 以降がサポートされます
- macOS デバイスに v95+ Edge ブラウザーをインストールする 

## <a name="onboard-macos-devices-into-microsoft-purview-solutions-using-microsoft-intune"></a>Microsoft Intuneを使用して macOS デバイスを Microsoft Purview ソリューションにオンボードする

MDE が既に展開されている場合は、次の手順に従って macOS デバイスをコンプライアンス ソリューションにオンボードします。

1. この手順では、これらのファイルが必要です。

|に必要なファイル |source |
|---------|---------|
|アクセシビリティ |[accessibility.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/profiles/accessibility.mobileconfig)|
フル ディスク アクセス     |[fulldisk.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/profiles/fulldisk.mobileconfig)|

> [!TIP]
> *.mobileconfig* ファイルは、個別にダウンロードすることも、次を含む [単一の結合ファイル](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/combined/mdatp-nokext.mobileconfig)でダウンロードすることもできます。
> - accessibility.mobileconfig
> - fulldisk.mobileconfig
> 
>
>これらの個々のファイルのいずれかが更新された場合は、結合されたファイルを再度ダウンロードするか、1 つの更新されたファイルを個別にダウンロードする必要があります。

### <a name="create-system-configuration-profiles"></a>システム構成プロファイルを作成する

1. **Microsoft エンドポイント マネージャー センター** > **のデバイス** > **構成プロファイルを開きます**。

1. [プロファイル **の作成**] を選択します。 

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

1. **デバイス** > **構成プロファイルを** 開くと、作成したプロファイルがそこに表示されます。

1. [ **構成プロファイル]** ページで、先ほど作成したプロファイルを選択し、この例の *[アクセシビリティフォームACOS* ] で [ **デバイスの状態** ] を選択して、デバイスの一覧と構成プロファイルの展開状態を表示します。

### <a name="update-existing-system-configuration-profiles"></a>既存のシステム構成プロファイルを更新する


1. フル ディスク アクセス構成プロファイルは、MDE 用に以前に作成およびデプロイされている必要があります。  [Mac でのMicrosoft Defender for EndpointのIntuneベースのデプロイを](/microsoft-365/security/defender-endpoint/mac-install-with-intune#full-disk-access)参照してください。 エンドポイント DLP には、新しいアプリケーション `com.microsoft.dlp.daemon`に対する追加のフル ディスク アクセス権限が必要です。 
    1. fulldisk.mobileconfig ファイルを使用して、既存の Fullfull Disk Access 構成プロファイルを更新します。 


1. 既存の MDE 環境設定プロファイルを見つけます。 [macOS でMicrosoft Defender for Endpointの環境設定を設定する](/microsoft-365/security/defender-endpoint/mac-preferences#intune-full-profile)
    1. 次の値を使用して、プロファイルに新しいキーを追加します。

```xml
<key>features</key> 
<dict> 
    <key>systemExtensions</key> 
    <string>enabled</string> 
    <key>dataLossPrevention</key> 
    <string>enabled</string> 
</dict> 
``` 

[mobileconfig の例](https://github.com/microsoft/mdatp-xplat/blob/master/macos/settings/data_loss_prevention/com.microsoft.wdav.mobileconfig)を次に示します。
 
## <a name="offboard-macos-devices-using-intune"></a>Intuneを使用したオフボード macOS デバイス

> [!IMPORTANT]
> オフボーディングにより、デバイスはポータルへのセンサー データの送信を停止しますが、デバイスからのデータ (発生したアラートへの参照を含む) は、最大 6 か月間保持されます。

1. **Microsoft エンドポイント マネージャー センター** でデバイス **構成プロファイル****を** > 開くと、作成したプロファイルがそこに表示されます。

2. [ **構成プロファイル] ページで** 、MDE 基本設定プロファイルを選択します。

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
