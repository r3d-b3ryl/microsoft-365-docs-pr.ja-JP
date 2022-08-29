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
ms.openlocfilehash: f71cc8f5ef0a0d9a251dca0b8da5e7797f553e0f
ms.sourcegitcommit: ab32c6e19af08837aaa84a058653c3a209d366ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2022
ms.locfileid: "67444965"
---
# <a name="onboard-and-offboard-macos-devices-into-microsoft-purview-solutions-using-intune"></a>Intune を使用した Microsoft Purview ソリューションへの macOS デバイスのオンボードとオフボード

Intuneを使用して、macOS デバイスを Microsoft Purview ソリューションにオンボードできます。

> [!IMPORTANT]
> macOS デバイスにMicrosoft Defender for Endpoint (MDE) が展開 ***されていない*** 場合は、次の手順を使用します。

**適用対象:**

- [エンドポイントのデータ損失防止](./endpoint-dlp-learn-about.md)
- [インサイダー リスク管理](insider-risk-management.md)

## <a name="before-you-begin"></a>はじめに

- [macOS デバイスがIntuneにオンボード](/mem/intune/fundamentals/deployment-guide-platform-macos)され、[ポータル サイト アプリ](/mem/intune/user-help/enroll-your-device-in-intune-macos-cp)に登録されていることを確認します。 
- [Microsoft エンドポイント マネージャー センター](https://endpoint.microsoft.com/#home)にアクセスできることを確認します。
- これにより、macOS の 3 つの最新のメジャー リリースがサポートされます。
- 構成の更新プログラムを割り当てるユーザー グループを作成します。
- macOS デバイスに v95+ Edge ブラウザーをインストールする 


## <a name="onboard-macos-devices-into-microsoft-purview-solutions-using-microsoft-intune"></a>Microsoft Intuneを使用して macOS デバイスを Microsoft Purview ソリューションにオンボードする

macOS デバイスをコンプライアンス ソリューションにオンボードすることは、多フェーズプロセスです。

1. [システム構成プロファイルを作成する](#create-system-configuration-profiles)
1. [デバイスのオンボード パッケージを取得する](#get-the-device-onboarding-package)
1. [mobileconfig パッケージとオンボード パッケージをデプロイする](#deploy-the-mobileconfig-and-onboarding-packages)
1. [アプリケーションの発行](#publish-application)
<!--1. [Enable system extension](#enable-system-extension)-->


### <a name="create-system-configuration-profiles"></a>システム構成プロファイルを作成する

1. この手順では、これらのファイルが必要です。 

|に必要なファイル |source |
|---------|---------|
システム モバイル構成ファイル | [mdatp-nokext.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/combined/mdatp-nokext.mobileconfig) テキスト ファイルに内容をコピーして貼り付けます。 **mobileconfig** 拡張子のみを使用してファイルを保存します。拡張子が.txtされている場合は認識されません。|
MDE の基本設定| [com.microsoft.wdav.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/settings/data_loss_prevention/com.microsoft.wdav.mobileconfig). 内容をコピーしてテキスト ファイルに貼り付けます。 **mobileconfig** 拡張子のみを使用してファイルを保存します。拡張子が.txtされている場合は認識されません。

### <a name="get-the-device-onboarding-package"></a>デバイスのオンボード パッケージを取得する

1. **Microsoft Purview コンプライアンス センター** で **、Settings****Device Onboarding** を > 開き、[**オンボード**] を選択します。
 
1. [ **オペレーティング システムを選択してオンボードプロセスを開始する** ] で **、macOS** を選択します。
 
1. **[展開方法]** で[**モバイル デバイス管理/Microsoft Intune**] を選択します。
 
1. [ **オンボード パッケージのダウンロード**] を選択します。 

1. zip ファイルを展開し、*Intune* フォルダーを開きます。 これには、 *DeviceComplianceOnboarding.xml* ファイルのオンボード コードが含まれます。

<!--|accessibility |[accessibility.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/profiles/accessibility.mobileconfig)|
full disk access     |[fulldisk.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/profiles/fulldisk.mobileconfig)|
|Network filer| [netfilter.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/profiles/netfilter.mobileconfig)]
|System extensions |[sysext.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/profiles/sysext.mobileconfig)
|MDE preference     |[com.microsoft.wdav.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/settings/data_loss_prevention/com.microsoft.wdav.mobileconfig)|
|MAU preference|[com.microsoft.autoupdate2.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/settings/microsoft_auto_update/com.microsoft.autoupdate2.mobileconfig)|
|Installation package     |downloaded from the compliance portal **Installation package**, file name *\*wdav.pkg*\* |

> [!TIP]
> You can download the *.mobileconfig* files individually or in [single combined file](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/combined/mdatp-nokext.mobileconfig) that contains:
> - accessibility.mobileconfig
> - fulldisk.mobileconfig
> - netfilter.mobileconfig
> - system extensions
>
>If any of these individual files is updated, you'd need to download the either the combined file again or the single updated file individually.-->

### <a name="deploy-the-mobileconfig-and-onboarding-packages"></a>mobileconfig パッケージとオンボード パッケージをデプロイする

1. **Microsoft エンドポイント マネージャー センター** > **のデバイス** > **構成プロファイルを開きます**。

1. 選択: **プロファイルの作成** 

1. 選択：
    1. **Platform = macOS**
    1. **プロファイルの種類 = テンプレート**
    1. **テンプレート名 = カスタム**

1. [**作成**] を選択する

1. この例の *SystemMobileConfig* のように、プロファイルの名前を選択します。 [**次へ**]を選択します。

1. 手順 1 でコピーして保存した **mdatp-nokext.mobileconfig** ファイルを構成プロファイル ファイルとして選択します。

1. **[次へ]** を選択します

1. [ **割り当て** ] タブで、これらの構成を展開するグループを追加し、[ **次へ**] を選択します。

1. 設定を確認し、[ **作成** ] を選択して構成をデプロイします。

1. 手順 2 ~ 9 を繰り返して、次のプロファイルを作成します。
    1. **DeviceComplianceOnboarding.xml** ファイル。 *Purview デバイス オンボーディング パッケージに名前を付けます*
    1. **com.microsoft.wdav.mobileconfig** ファイル。 *エンドポイント デバイスの基本設定* に名前を付けます
 
1. **デバイス** > **構成プロファイルを** 開くと、作成したプロファイルがそこに表示されます。

1. [ **構成プロファイル]** ページで、作成したプロファイル ( *SystemMobileConfig* など) を選択し、[ **デバイスの状態]** を選択して、デバイスの一覧と構成プロファイルの展開状態を表示します。

### <a name="publish-application"></a>アプリケーションの発行

Microsoft Endpoint DLP は、macOS 上の Microsoft Defender for Endpoint (MDE) のコンポーネントとしてインストールされます。 この手順は、Microsoft Purview ソリューションへのデバイスのオンボードに適用されます

1. [Microsoft エンドポイント マネージャー管理センター](https://endpoint.microsoft.com/)で、アプリを開 **きます**。

1. [プラットフォーム別] > macOS > [追加] を選択します。

1. **[アプリの種類**=**] macOS** を選択し、[**選択**] をクリックします。

1. 既定値のままにして、[ **次へ**] をクリックします。

1. 割り当てを追加し、[ **次へ**] をクリックします。

1. 確認と **作成**。

1. **Apps** \> **By platform** \> **macOS** にアクセスすると、すべてのアプリケーションの一覧に表示されます。

<!--## Offboard macOS devices using Intune PINGING PG FOR THIS PROCEDURE

> [!NOTE]
> Offboarding causes the device to stop sending sensor data to the portal but data from the device, including reference to any alerts it has had will be retained for up to six months.

1. In **Microsoft Endpoint Manager center**, open **Devices** > **Configuration profiles**, you should see your created profiles there.

1. In the **Configuration profiles** page, choose the *wdav.pkg.intunemac* profile.

1. Choose **Device status** to see a list of devices and the deployment status of the configuration profile

1. Open **Properties** and **Assignments**

1. Remove the group from the assignment. This will uninstall the *wdav.pkg.intunemac* package and offboard the macOS device from Compliance solutions.-->
