---
title: JAMF Pro を使用した Microsoft 365 コンプライアンス ソリューションへの macOS デバイスのオンボードとオフボード (プレビュー)
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
description: JAMF ソリューション (プレビュー) を使用して、macOS デバイスをオンボードおよびオフボードMicrosoft 365コンプライアンス ソリューションにProする方法について学習します。
ms.openlocfilehash: 1c21251b390209d92696a36962705b9f2517a53c
ms.sourcegitcommit: 1ef176c79a0e6dbb51834fe30807409d4e94847c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/19/2021
ms.locfileid: "61111221"
---
# <a name="onboard-and-offboard-macos-devices-into-microsoft-365-compliance-solutions-using-jamf-pro-preview"></a>JAMF Pro を使用した Microsoft 365 コンプライアンス ソリューションへの macOS デバイスのオンボードとオフボード (プレビュー)

JAMF デバイスを使用Pro、エンドポイント データ損失防止Microsoft 365コンプライアンス ソリューションに macOS デバイスをオンボードできます。

> [!IMPORTANT]
> MacOS デバイスにMicrosoft Defender for Endpoint (MDE) が展開されていない場合は、次の手順を実行します。

## <a name="get-registered"></a>登録する

この機能にアクセスするには、テナントを Microsoft に登録する必要があります。 [Microsoft 365 macOS サポート](https://aka.ms/EndpointDLPIgnite21-Previews)に登録します。

**適用対象:**

- [Microsoft 365 エンドポイントのデータ損失防止 (DLP)](./endpoint-dlp-learn-about.md)
- [インサイダー リスク管理](insider-risk-management.md#learn-about-insider-risk-management-in-microsoft-365)

## <a name="before-you-begin"></a>はじめに

- [macOS デバイスが参加Azure ADする](https://docs.jamf.com/10.30.0/jamf-pro/administrator-guide/Azure_AD_Integration.html)
- macOS デバイスが JAMF pro [を介して管理されている必要があります。](https://www.jamf.com/resources/product-documentation/jamf-pro-installation-guide-for-mac/)
- macOS デバイスに v95+ Edge ブラウザーをインストールする 

## <a name="onboard-devices-into-microsoft-365-compliance-solutions-using-jamf-pro"></a>JAMF を使用してMicrosoft 365コンプライアンス ソリューションにデバイスをオンボードPro

1. この手順では、これらのファイルが必要です。

|必要なファイル |ソース |
|---------|---------|
|オンボーディング パッケージ    |コンプライアンス ポータルオンボード パッケージ **、ファイル名** *DeviceComplianceOnboarding.plist からダウンロード* |
|アクセシビリティ |[アクセシビリティ.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/profiles/accessibility.mobileconfig)|
フル ディスク アクセス     |[fulldisk.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/profiles/fulldisk.mobileconfig)|
|ネットワーク フィルター| [netfilter.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/profiles/netfilter.mobileconfig)
|システム拡張機能 |[sysext.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/profiles/systext.mobileconfig)
|MDE の基本設定     |[schema.json](https://github.com/microsoft/mdatp-xplat/blob/master/macos/settings/data_loss_prevention/schema.json)|
|MAU の基本設定|[com.microsoft.autoupdate2.plist](https://github.com/microsoft/mdatp-xplat/blob/master/macos/settings/microsoft_auto_update/com.microsoft.autoupdate2.plist)|
|インストール パッケージ     |コンプライアンス ポータルのインストール パッケージ **からダウンロードされた** ファイル名 *\* wdav.pkg*\* |

> [!TIP]
> *.mobileconfig* ファイルは、個別にダウンロードするか、以下を含 [む単一の結合ファイル](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/combined/mdatp-nokext.mobileconfig)でダウンロードできます。
> - アクセシビリティ.mobileconfig
> - fulldisk.mobileconfig
> - netfilter.mobileconfig
> - sysext.mobileconfig
>
>これらの個々のファイルが更新された場合は、結合されたファイルを再度ダウンロードするか、単一の更新されたファイルを個別にダウンロードする必要があります。

コンプライアンス ソリューションへの macOS デバイスのオンボーディングは、複数フェーズのプロセスです。

### <a name="get-the-device-onboarding-package"></a>デバイスオンボーディング パッケージの取得

1. コンプライアンス **センターで[デバイスオン** ボーディング **設定**  >  **開き**、[オンボーディング]**を選択します**。
 
1. [ **オンボーディング プロセスを開始するオペレーティング システムの選択] で** **macOS を選択する**
 
1. [**展開方法] で**[**モバイル デバイスの管理/管理] を選択Microsoft Intune**
 
1. [オンボード **パッケージのダウンロード] を選択する**
 
1. デバイスオンボーディング パッケージの内容を抽出します。 JAMF フォルダーに *DeviceComplainceOnboarding.plist ファイルが表示* されます。

### <a name="create-a-jamf-pro-configuration-profile-for-the-onboarding-package"></a>オンボード パッケージの JAMF Pro構成プロファイルを作成する

1. JAMF サーバーで新しい構成プロファイルをPro。 [JAMF 管理者ガイドPro参照してください](https://www.jamf.com/resources/product-documentation/jamf-pro-administrators-guide/)。 次の値を使用します。
    - 名前: `MDATP onboarding for macOS`
    - 説明: `MDATP EDR onboarding for macOS`
    - カテゴリ: `none`
    - 配布方法: `install automatically`
    - レベル: `computer level`

2. JAMF コンソールで、[アプリケーション Pro **カスタム>設定**&**アップロード]** を選択し、[追加] を **選択します**。 次の値を使用します。
    - 基本設定ドメイン: `com.microsoft.wdav.atp`

3. [ **アップロード] を** 選択し、オンボード ファイル **DeviceComplianceOnboarding.plist を選択します**。

4. [スコープ] **タブを選択** します。

5. ターゲット コンピューターを選択します。

6. **[保存]** を選択します。

7. [**完了**] を選択します。

### <a name="configure-preference-domain-using-the-jamf-pro-console"></a>JAMF PRO コンソールを使用して基本設定ドメインを構成する

> [!IMPORTANT]
> 基本設定ドメインの **値として * com.microsoft.wdav** _ を使用する必要があります。 Microsoft Defender for Endpoint では、この名前と _ *_com.microsoft.wdav.ext_** を使用して管理設定を読み込む。

1. JAMF サーバーで新しい構成プロファイルをPro。 [JAMF 管理者ガイドPro参照してください](https://www.jamf.com/resources/product-documentation/jamf-pro-administrators-guide/)。 次の値を使用します。
    - 名前: `MDATP MDAV configuration settings`
    - 説明: 空白のままにする
    - カテゴリ: `none`
    - 配布方法: `install automatically`
    - レベル: `computer level`

1. [アプリケーション **]&[** カスタム 設定] タブで、[外部アプリケーション] を選択し、[追加] を選択し、基本設定ドメインの [カスタム **スキーマ**] を選択します。 次の値を使用します。
    - 基本設定ドメイン: `com.microsoft.wdav`

1. [**スキーマの追加]** **をアップロード** スキーマ *.json ファイルをアップロード* します。

1. **[保存]** を選択します。

1. [基本 **設定ドメインのプロパティ] で、** これらの設定を選択します。
    - 機能 
        - システム拡張機能の使用: `enabled` - Catalina のネットワーク拡張機能に必要
        - データ損失防止の使用: `enabled`
    - ウイルス対策エンジン>パッシブ モード: `true|false` . DLP `true` のみを展開する場合に使用します。 DLP と Microsoft Defender for Endpoint (MDE) を展開する場合は、値を使用するか `false` 、割り当てない。

1. [スコープ] **タブを選択** します。

1. この構成プロファイルを展開するグループを選択します。

1. **[保存]** を選択します。 


### <a name="create-and-deploy-a-configuration-profile-for-microsoft-autoupdate-mau"></a>Microsoft AutoUpdate (MAU) の構成プロファイルを作成して展開する

1. **com.microsoft.autoupdate2.plist** を使用Pro JAMF 構成ファイルを作成します。 [JAMF 管理者ガイドPro参照してください](https://www.jamf.com/resources/product-documentation/jamf-pro-administrators-guide/)。 次の値を使用します。
    - 名前: `MDATP MDAV MAU settings`
    - 説明: `Microsoft AutoUPdate settings for MDATP for macOS`
    - カテゴリ: `none`
    - 配布方法: `install automatically`
    - レベル: `computer level`

1. [**アプリケーション] & カスタム 設定、[** **アップロード] を****選択します**。

1. [**基本設定] ドメインに** 入力 `com.microsoft.autoupdate2` し、[設定]**をアップロード。**

1. **com.microsoft.autoupdate2.plist ファイルを選択** します。

1. **[保存]** を選択します。

1. [スコープ] **タブを選択** します。

1. ターゲット コンピューターを選択します。

1. **[保存]** を選択します。

1. [**完了**] を選択します。


### <a name="create-and-deploy-a-configuration-profile-for-grant-full-disk-access"></a>フル ディスク アクセスを許可する構成プロファイルを作成して展開する

1. **fulldisk.mobileconfig ファイルを使用** します。

1. **アップロードdisk.mobileconfig ファイルを** JAMF に移動します。 [「JAMF を使用したカスタム構成プロファイルの展開」を参照Pro。](https://docs.jamf.com/technical-articles/Deploying_Custom_Configuration_Profiles_Using_Jamf_Pro.html)

### <a name="create-and-deploy-a-configuration-profile-for-system-extensions"></a>システム拡張機能の構成プロファイルを作成して展開する

1. JAMF 管理者ガイドのProを使用して[、JAMF Pro構成ファイルを作成します](https://www.jamf.com/resources/product-documentation/jamf-pro-administrators-guide/)。 次の値を使用します。
    - 名前: `MDATP MDAV System Extensions`
    - 説明: `MDATP system extensions`
    - カテゴリ: `none`
    - 配布方法: `install automatically`
    - レベル: `computer level`

1. [System **extentions profile]** で、次の値を入力します。
    - 表示名: `Microsoft Corp. System Extensions`
    - System Extenstion の種類: `Allowed System Extensions`
    - チーム識別子: `UBF8T346G9`
    - 許可されるシステム拡張機能: `com.microsoft.wdav.epsext` 、および `com.microsoft.wdav.netext`

1. [スコープ] **タブを選択** します。

1. ターゲット コンピューターを選択します。

1. **[保存]** を選択します。

1. [**完了**] を選択します。

### <a name="configure-network-extension"></a>ネットワーク拡張機能の構成

1.  Github **からダウンロードした netfilter.mobileconfig**  ファイルを使用します。

2.  アップロードを使用したカスタム構成プロファイルの展開」の説明に従って[JAMF](https://www.jamf.com/jamf-nation/articles/648/deploying-custom-configuration-profiles-using-jamf-pro)にPro。

### <a name="grant-accessibility-access-to-dlp"></a>DLP へのアクセシビリティ アクセスを許可する

1. Github **からダウンロードしたアクセシビリティ.mobileconfig** ファイルを使用します。

2.  アップロードを使用したカスタム構成プロファイルの展開」の説明に従って[JAMF](https://www.jamf.com/jamf-nation/articles/648/deploying-custom-configuration-profiles-using-jamf-pro)にPro。

### <a name="get-the-installation-package"></a>インストール パッケージの取得

1. コンプライアンス **センターで[デバイスオン** ボーディング **設定**  >  **開き**、[オンボーディング]**を選択します**。
 
1. [ **オンボーディング プロセスを開始するオペレーティング システムの選択] で** **macOS を選択する**
 
1. [**展開方法] で**[**モバイル デバイスの管理/管理] を選択Microsoft Intune**
 
1. [インストール **パッケージのダウンロード] を選択します**。 これにより *、wdav.pkg ファイルが表示* されます。


### <a name="deploy-the-installation-package"></a>インストール パッケージの展開

1. ファイルを保存した場所に `wdav.pkg` 移動します。

1. JAMF ダッシュボードをProします。

1. コンピューターを選択し、上部の歯車をクリックし、[コンピューターの管理] **を選択します**。

1. [パッケージ **] で** **[+新規] を選択します**。 次の詳細を入力します。
    - 表示名: .pkg ファイルを選択するとリセットされますので、空白のままにします。
    - カテゴリ: なし (既定)
    - Filname: [ファイル] (この場合はファイル) を選択 `wdav.pkg` します。

1. [ **開く**] を選択します。 セット:
    - **表示名**: `Microsoft Endpoint Technology`
    - **マニフェスト ファイル**: 必須ではありません
    - **[オプション] タブ**: 既定値のままにする
    - **[制限] タブ**: 既定値のままにする

1. **[保存]** を選択します。 これにより、パッケージが JAMF ファイルにPro。

1. [ポリシー] **ページを開** きます。

1. **[+New] を選択** して新しいポリシーを作成します。

1. これらの値を入力する
    - **表示名**: `MDATP Onboarding200329 v100.86.92 or later`

1. [ **定期的なチェックイン] を選択します**。

1. **[保存]** を選択します。

1. [パッケージ **の構成]**  >  **を選択します**。

1. **[追加]** を選択します。

1. **[保存]** を選択します。 

1. [スコープ] **タブを選択** します。

1. ターゲット コンピューターを選択します。

1. **[追加]** を選択します。

1. [セルフサービス **] を選択します**。

1. [**完了**] を選択します。

### <a name="check-the-macos-device"></a>macOS デバイスを確認する 

1. macOS デバイスを再起動します。

1. [**システム設定プロファイル]**  >  **を開きます**。

1. 次の情報が表示されます。
    - アクセシブル
    - フル ディスク アクセス
    - MAU
    - MDATP オンボーディング
    - MDE の基本設定
    - 管理プロファイル
    - ネットワーク フィルター
    - システム拡張プロファイル

## <a name="offboard-macos-devices-using-jamf-pro"></a>JAMF デバイスを使用するオフボード macOS Pro

1. アプリケーションをアンインストールする (MDE を使用しない場合)
    1. 「JAMF Pro ドキュメント - パッケージの展開 - [JAMF](https://www.jamf.com/resources/product-documentation/jamf-pro-administrators-guide/)Pro管理者ガイド Jamf Pro管理者ガイド」を参照してください。

1. macOS デバイスを再起動する - 一部のアプリケーションは、再起動するまで印刷機能が失われる可能性があります

> [!IMPORTANT]
> Offboarding を使用すると、デバイスはポータルへのセンサー データの送信を停止しますが、デバイスからのデータ (通知への参照を含む) は最大 6 か月間保持されます。
