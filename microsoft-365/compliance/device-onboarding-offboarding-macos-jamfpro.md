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
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: JAMF Pro (プレビュー) を使用して macOS デバイスをMicrosoft 365コンプライアンス ソリューションにオンボードおよびオフボードする方法について説明します
ms.openlocfilehash: 44e57e482c08b486563200010671b5c79329f7b2
ms.sourcegitcommit: ac0ae5c2888e2b323e36bad041a4abef196c9c96
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/12/2022
ms.locfileid: "64783823"
---
# <a name="onboard-and-offboard-macos-devices-into-microsoft-365-compliance-solutions-using-jamf-pro-preview"></a>JAMF Pro を使用した Microsoft 365 コンプライアンス ソリューションへの macOS デバイスのオンボードとオフボード (プレビュー)

JAMF Proを使用して、macOS デバイスをエンドポイントデータ損失防止などのMicrosoft 365コンプライアンス ソリューションにオンボードできます。

> [!IMPORTANT]
> macOS デバイスにMicrosoft Defender for Endpoint (MDE) が展開 ***されていない*** 場合は、次の手順を使用します。

**適用対象:**

- [Microsoft 365 エンドポイントのデータ損失防止 (DLP)](./endpoint-dlp-learn-about.md)
- [インサイダー リスク管理](insider-risk-management.md#learn-about-insider-risk-management-in-microsoft-365)

## <a name="before-you-begin"></a>はじめに

- [macOS デバイスが JAMF pro を介して管理され、JAMF](https://www.jamf.com/resources/product-documentation/jamf-pro-installation-guide-for-mac/) ConnectまたはIntuneを介して ID (Azure AD参加している UPN) に関連付けられていることを確認します。
- macOS デバイスに v95+ Edge ブラウザーをインストールする

## <a name="onboard-devices-into-microsoft-365-compliance-solutions-using-jamf-pro"></a>JAMF Proを使用してデバイスをMicrosoft 365コンプライアンス ソリューションにオンボードする

1. この手順では、これらのファイルが必要です。

|に必要なファイル|ソース|
|---|---|
|オンボード パッケージ|コンプライアンス ポータルの **オンボード パッケージ** からダウンロードしたファイル名 *DeviceComplianceOnboarding.plist*|
|アクセシビリティ|[accessibility.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/profiles/accessibility.mobileconfig)|
フル ディスク アクセス|[fulldisk.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/profiles/fulldisk.mobileconfig)|
|ネットワーク フィルター| [netfilter.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/profiles/netfilter.mobileconfig)
|システム拡張機能|[sysext.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/profiles/sysext.mobileconfig)
|MDE の基本設定|[schema.json](https://github.com/microsoft/mdatp-xplat/blob/master/macos/settings/data_loss_prevention/schema.json)|
|MAU の基本設定|[com.microsoft.autoupdate2.plist](https://github.com/microsoft/mdatp-xplat/blob/master/macos/settings/microsoft_auto_update/com.microsoft.autoupdate2.plist)|
|インストール パッケージ|コンプライアンス ポータルの **インストール パッケージ** からダウンロードしたファイル名 *\*wdav.pkg*\*|

> [!TIP]
> *.mobileconfig* ファイルは、個別にダウンロードすることも、次を含む [単一の結合ファイル](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/combined/mdatp-nokext.mobileconfig)でダウンロードすることもできます。
>
> - accessibility.mobileconfig
> - fulldisk.mobileconfig
> - netfilter.mobileconfig
> - sysext.mobileconfig
>
>これらの個々のファイルのいずれかが更新された場合は、結合されたファイルを再度ダウンロードするか、1 つの更新されたファイルを個別にダウンロードする必要があります。

macOS デバイスをコンプライアンス ソリューションにオンボードすることは、多相的なプロセスです。

### <a name="get-the-device-onboarding-package"></a>デバイスのオンボード パッケージを取得する

1. **コンプライアンス センター** で **、設定** > **Device オンボードを** 開き、[**オンボード**] を選択します。

1. オペレーティング **システムを選択してオンボードプロセスを開始するには****、macOS** を選択します

1. **[展開方法]** で [**モバイル デバイス管理/Microsoft Intune**] を選択します

1. **[オンボード パッケージのダウンロード**] を選択する

1. デバイスオンボード パッケージの内容を抽出します。 JAMF フォルダーに *DeviceComplainceOnboarding.plist* ファイルが表示されます。

### <a name="create-a-jamf-pro-configuration-profile-for-the-onboarding-package"></a>オンボード パッケージの JAMF Pro構成プロファイルを作成する

1. JAMF Proで新しい構成プロファイルを作成します。 [JAMF Pro管理者ガイドを](https://www.jamf.com/resources/product-documentation/jamf-pro-administrators-guide/)参照してください。 次の値を使用します。
    - 名前: `MDATP onboarding for macOS`
    - 説明： `MDATP EDR onboarding for macOS`
    - カテゴリ： `none`
    - 分布方法: `install automatically`
    - レベル： `computer level`

2. JAMF Pro コンソール>**アプリケーション&カスタム設定** で、**アップロード** を選択して **追加** します。 次の値を使用します。
    - 基本設定ドメイン: `com.microsoft.wdav.atp`

3. **アップロード** を選択し、オンボード ファイル **DeviceComplianceOnboarding.plist** を選択します。

4. **[スコープ**] タブを選択します。

5. ターゲット コンピューターを選択します。

6. **[保存]** を選択します。

7. [**完了**] を選択します。

### <a name="configure-preference-domain-using-the-jamf-pro-console"></a>JAMF PRO コンソールを使用して基本設定ドメインを構成する

> [!IMPORTANT]
> 基本設定ドメインの値として ***com.microsoft.wdav** _ を使用する必要があります。 Microsoft Defender for Endpointでは、この名前と _ *_com.microsoft.wdav.ext_** を使用して管理設定を読み込みます。

1. JAMF Proで新しい構成プロファイルを作成します。 [JAMF Pro管理者ガイドを](https://www.jamf.com/resources/product-documentation/jamf-pro-administrators-guide/)参照してください。 次の値を使用します。
    - 名前: `MDATP MDAV configuration settings`
    - 説明: 空白のままにする
    - カテゴリ： `none`
    - 分布方法: `install automatically`
    - レベル： `computer level`

1. [**アプリケーション & カスタム 設定**] タブで、[**外部アプリケーション**] を選択し、[**追加**] を選択し、基本設定ドメインの **[カスタム スキーマ**] を選択します。 次の値を使用します。
    - 基本設定ドメイン: `com.microsoft.wdav`

1. [**スキーマの追加]** を選択し **、アップロード***を選択して schema.json* ファイルをアップロードします。

1. **[保存]** を選択します。

1. **[基本設定ドメインのプロパティ] で** これらの設定を選択します
    - 機能
        - システム拡張機能を使用する: `enabled` - Catalina のネットワーク拡張機能に必要です
        - データ損失防止を使用する: `enabled`
    - ウイルス対策エンジン>パッシブ モード: `true|false`. DLP のみを展開する場合に使用します `true`。 DLP とMicrosoft Defender for Endpoint (MDE) を展開する場合は、値を使用`false`するか、割り当てないでください。

1. [ **スコープ** ] タブを選択します。

1. この構成プロファイルをデプロイするグループを選択します。

1. **[保存]** を選択します。

### <a name="create-and-deploy-a-configuration-profile-for-microsoft-autoupdate-mau"></a>Microsoft AutoUpdate (MAU) の構成プロファイルを作成して展開する

1. **com.microsoft.autoupdate2.plist** を使用して JAMF Pro構成ファイルを作成します。 [JAMF Pro管理者ガイドを](https://www.jamf.com/resources/product-documentation/jamf-pro-administrators-guide/)参照してください。 次の値を使用します。
    - 名前: `MDATP MDAV MAU settings`
    - 説明： `Microsoft AutoUPdate settings for MDATP for macOS`
    - カテゴリ： `none`
    - 分布方法: `install automatically`
    - レベル： `computer level`

1. **アプリケーション & カスタム 設定** で **、アップロード** と追加を選択 **します**。

1. **[基本設定のドメイン] に**「アップロード」と入力`com.microsoft.autoupdate2`**して選択します**。

1. **com.microsoft.autoupdate2.plist ファイルを** 選択します。

1. **[保存]** を選択します。

1. [ **スコープ** ] タブを選択します。

1. ターゲット コンピューターを選択します。

1. **[保存]** を選択します。

1. [**完了**] を選択します。

### <a name="create-and-deploy-a-configuration-profile-for-grant-full-disk-access"></a>フル ディスク アクセスを許可するための構成プロファイルを作成してデプロイする

1. **fulldisk.mobileconfig** ファイルを使用します。

1. **fulldisk.mobileconfig** ファイルを JAMF にアップロードします。 [JAMF Proを使用したカスタム構成プロファイルのデプロイ](https://docs.jamf.com/technical-articles/Deploying_Custom_Configuration_Profiles_Using_Jamf_Pro.html)に関する説明を参照してください。

### <a name="create-and-deploy-a-configuration-profile-for-system-extensions"></a>システム拡張機能の構成プロファイルを作成してデプロイする

1. JAMF Pro管理者ガイドの手順を使用して[、JAMF Pro](https://www.jamf.com/resources/product-documentation/jamf-pro-administrators-guide/)構成ファイルを作成します。 次の値を使用します。
    - 名前: `MDATP MDAV System Extensions`
    - 説明： `MDATP system extensions`
    - カテゴリ： `none`
    - 分布方法: `install automatically`
    - レベル： `computer level`

1. **システム拡張機能** プロファイルで、次の値を入力します。
    - 表示名: `Microsoft Corp. System Extensions`
    - システム拡張機能の種類: `Allowed System Extensions`
    - チーム識別子: `UBF8T346G9`
    - 許可されるシステム拡張機能: `com.microsoft.wdav.epsext`、および `com.microsoft.wdav.netext`

1. [ **スコープ** ] タブを選択します。

1. ターゲット コンピューターを選択します。

1. **[保存]** を選択します。

1. [**完了**] を選択します。

### <a name="configure-network-extension"></a>ネットワーク拡張機能を構成する

1. GitHubからダウンロードした **netfilter.mobileconfig** ファイルを使用します。

2. [Jamf Proを使用したカスタム構成プロファイルのデプロイ](https://www.jamf.com/jamf-nation/articles/648/deploying-custom-configuration-profiles-using-jamf-pro)に関する説明に従って JAMF にアップロードします。

### <a name="grant-accessibility-access-to-dlp"></a>DLP へのアクセシビリティ アクセスを付与する

1. GitHubからダウンロードした **accessibility.mobileconfig** ファイルを使用します。

2. [Jamf Proを使用したカスタム構成プロファイルのデプロイ](https://www.jamf.com/jamf-nation/articles/648/deploying-custom-configuration-profiles-using-jamf-pro)に関する説明に従って JAMF にアップロードします。

### <a name="get-the-installation-package"></a>インストール パッケージを取得する

1. **コンプライアンス センター** で **、設定** > **Device オンボードを** 開き、[**オンボード**] を選択します。

1. オペレーティング **システムを選択してオンボードプロセスを開始するには****、macOS** を選択します

1. **[展開方法]** で [**モバイル デバイス管理/Microsoft Intune**] を選択します

1. [ **インストール パッケージのダウンロード**] を選択します。 これにより、 *wdav.pkg* ファイルが提供されます。

### <a name="deploy-the-installation-package"></a>インストール パッケージをデプロイする

1. ファイルを保存した場所に `wdav.pkg` 移動します。

1. JAMF Pro ダッシュボードを開きます。

1. コンピューターを選択し、上部にある歯車をクリックしてから、[ **コンピューターの管理**] を選択します。

1. **[パッケージ**] で [**+新規**] を選択します。 次の詳細を入力します。
    - 表示名: .pkg ファイルを選択するとリセットされるため、空白のままにします。
    - カテゴリ: なし (既定)
    - ファイル名: ファイル (この場合はファイル) を `wdav.pkg` 選択します。

1. [ **開く**] を選択します。 設定：
    - **表示名**: `Microsoft Endpoint Technology`
    - **マニフェスト ファイル**: 必須ではありません
    - **[オプション] タブ**: 既定値のままにする
    - **[制限事項] タブ**: 既定値のままにする

1. **[保存]** を選択します。 これにより、パッケージが JAMF Proにアップロードされます。

1. **[ポリシー] ページを** 開きます。

1. **[+新規]** を選択して新しいポリシーを作成します。

1. これらの値を入力します
    - **表示名**: `MDATP Onboarding200329 v100.86.92 or later`

1. [ **定期的なチェックイン**] を選択します。

1. **[保存]** を選択します。

1. **[PackagesConfigure** > ] を選択 **します**。

1. **[追加]** を選択します。

1. **[保存]** を選択します。

1. [ **スコープ** ] タブを選択します。

1. ターゲット コンピューターを選択します。

1. **[追加]** を選択します。

1. [ **セルフサービス**] を選択します。

1. [**完了**] を選択します。

### <a name="check-the-macos-device"></a>macOS デバイスを確認する

1. macOS デバイスを再起動します。

1. **System PreferencesProfiles** >  を開 **きます**。

1. 次の情報が表示されます。
    - アクセシビリティ
    - フル ディスク アクセス
    - マウ
    - MDATP オンボード
    - MDE 環境設定
    - 管理プロファイル
    - ネットワーク フィルター
    - システム拡張機能プロファイル

## <a name="offboard-macos-devices-using-jamf-pro"></a>JAMF Proを使用したオフボード macOS デバイス

1. アプリケーションをアンインストールする (MDE を使用していない場合)
    1. JAMF Pro Docs - パッケージの展開 - [JAMF Pro管理者ガイド](https://www.jamf.com/resources/product-documentation/jamf-pro-administrators-guide/)Jamf Pro管理者ガイドを参照してください

1. macOS デバイスを再起動する - 一部のアプリケーションは、再起動するまで印刷機能を失う可能性があります

> [!IMPORTANT]
> オフボーディングにより、デバイスはポータルへのセンサー データの送信を停止しますが、デバイスからのデータ (発生したアラートへの参照を含む) は、最大 6 か月間保持されます。
