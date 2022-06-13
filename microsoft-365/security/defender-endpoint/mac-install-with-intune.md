---
title: Mac でのMicrosoft Defender for EndpointのIntune ベースのデプロイ
description: Microsoft Intuneを使用して Mac にMicrosoft Defender for Endpointをインストールします。
keywords: microsoft, defender, Microsoft Defender for Endpoint, mac, インストール, 展開, アンインストール, intune, jamf, macos, catalina, mojave, high sierra
ms.prod: m365-security
ms.mktglfcycl: deploy
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
ms.openlocfilehash: 4c2c1f7c11c57ca45411b74023807077f73ba8bf
ms.sourcegitcommit: a7c1acfb3d2cbba913e32493b16ebd8cbfeee456
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/13/2022
ms.locfileid: "66044108"
---
# <a name="intune-based-deployment-for-microsoft-defender-for-endpoint-on-macos"></a>macOSでのMicrosoft Defender for EndpointのIntune ベースのデプロイ

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**

- [macOS 用 Microsoft Defender for Endpoint](microsoft-defender-endpoint-mac.md)
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

このトピックでは、Intuneを介してmacOSにMicrosoft Defender for Endpointをデプロイする方法について説明します。 デプロイが正常に完了するには、次のすべての手順を完了する必要があります。

1. [オンボーディング パッケージをダウンロードする](#download-the-onboarding-package)
1. [クライアント デバイスのセットアップ](#client-device-setup)
1. [システム拡張機能を承認する](#approve-system-extensions)
1. [システム構成プロファイルを作成する](#create-system-configuration-profiles)
1. [アプリケーションの発行](#publish-application)

## <a name="prerequisites-and-system-requirements"></a>前提条件とシステム要件

作業を開始する前に、現在のソフトウェア バージョンの前提条件とシステム要件の説明については、[macOS ページのメイン](microsoft-defender-endpoint-mac.md) Microsoft Defender for Endpointを参照してください。

## <a name="overview"></a>概要

次の表は、Intune経由で Mac でMicrosoft Defender for Endpointを展開および管理するために必要な手順をまとめたものです。 詳細な手順については、以下をご覧ください。

<br>

****

|手順|サンプル ファイル名|BundleIdentifier|
|---|---|---|
|[オンボーディング パッケージをダウンロードする](#download-the-onboarding-package)|WindowsDefenderATPOnboarding__MDATP_wdav.atp.xml|com.microsoft.wdav.atp|
|[Microsoft Defender for Endpointのシステム拡張機能を承認する](#approve-system-extensions)|MDATP_SysExt.xml|該当なし|
|[Microsoft Defender for Endpointのカーネル拡張機能を承認する](#download-the-onboarding-package)|MDATP_KExt.xml|該当なし|
|[Microsoft Defender for Endpointへのフル ディスク アクセスを許可する](#full-disk-access)|MDATP_tcc_Catalina_or_newer.xml|com.microsoft.wdav.tcc|
|[ネットワーク拡張機能ポリシー](#network-filter)|MDATP_NetExt.xml|該当なし|
|[Microsoft AutoUpdate (MAU) の構成](mac-updates.md#intune)|MDATP_Microsoft_AutoUpdate.xml|com.microsoft.autoupdate2|
|[Microsoft Defender for Endpoint構成設定](mac-preferences.md#intune-full-profile) <p> **メモ：** macOSのサード パーティ製 AV を実行する予定がある場合は、 `passiveMode` `true`.|MDATP_WDAV_and_exclusion_settings_Preferences.xml|com.microsoft.wdav|
|[Microsoft Defender for Endpointおよび MS AutoUpdate (MAU) 通知を構成する](mac-updates.md)|MDATP_MDAV_Tray_and_AutoUpdate2.mobileconfig|com.microsoft.autoupdate2 または com.microsoft.wdav.tray|
|

## <a name="download-the-onboarding-package"></a>オンボーディング パッケージをダウンロードする

Microsoft 365 Defender ポータルからオンボード パッケージをダウンロードします。

1. Microsoft 365 Defender ポータルで、**設定** \> **Endpoints** \> **デバイス管理** \> **オンボード** に移動します。

2. オペレーティング システムを **macOS** に設定し、展開方法を **Mobile デバイス管理/Microsoft Intune** に設定します。

   :::image type="content" source="images/macos-install-with-intune.png" alt-text="[オンボード設定] ページ" lightbox="images/macos-install-with-intune.png":::

3. **[オンボーディング パッケージをダウンロードする]** を選択します。 同じディレクトリに _WindowsDefenderATPOnboardingPackage.zip_ として保存します。

4. .zip ファイルの内容を抽出します。

    ```bash
    unzip WindowsDefenderATPOnboardingPackage.zip
    ```

    ```Output
    Archive:  WindowsDefenderATPOnboardingPackage.zip
    warning:  WindowsDefenderATPOnboardingPackage.zip appears to use backslashes as path separators
      inflating: intune/kext.xml
      inflating: intune/WindowsDefenderATPOnboarding.xml
      inflating: jamf/WindowsDefenderATPOnboarding.plist
    ```

## <a name="create-system-configuration-profiles"></a>システム構成プロファイルを作成する

次の手順では、必要なシステム構成プロファイルMicrosoft Defender for Endpoint作成します。
[Microsoft エンドポイント マネージャー管理センター](https://endpoint.microsoft.com/)で、デバイス **構成プロファイル****を**\>開きます。

### <a name="onboarding-blob"></a>BLOB のオンボード

このプロファイルには、Microsoft Defender for Endpointのライセンス情報が含まれています。 このプロファイルがない場合、Microsoft Defender for Endpointはライセンスが付与されていないことを報告します。

1. [構成 **プロファイル]** で [ **プロファイルの作成] を選択します**。
1. **[プラットフォーム**=**macOS****プロファイルの種類** テンプレート] を選択 **します**=。 **テンプレート名**=**カスタム**。 **[作成]** をクリックします。

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="images/mdatp-6-systemconfigurationprofiles-1.png" alt-text="[カスタム構成プロファイルの作成] ページ" lightbox="images/mdatp-6-systemconfigurationprofiles-1.png":::

1. プロファイルの名前 ("macOSのDefender for Cloudまたはエンドポイントオンボード" など) を選択します。 **[次へ]** をクリックします。

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="images/mdatp-6-systemconfigurationprofiles-2.png" alt-text="[カスタム構成プロファイル名] フィールド" lightbox="images/mdatp-6-systemconfigurationprofiles-2.png":::

1. 構成プロファイル名の名前を選択します (例: "macOS用の Defender for Endpoint onboarding)。
1. [デプロイ チャネル](/mem/intune/fundamentals/whats-new#new-deployment-channel-setting-for-custom-device-configuration-profiles-on-macos-devices)を選択します。
1. 上のオンボード パッケージから抽出した intune/WindowsDefenderATPOnboarding.xmlを構成プロファイル ファイルとして選択します。

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="images/mdatp-6-systemconfigurationprofiles.png" alt-text="カスタム構成プロファイルのファイルからの構成のインポート" lightbox="images/mdatp-6-systemconfigurationprofiles.png":::

1. **[次へ]** をクリックします。
1. [ **割り当て** ] タブでデバイスを割り当てます。 **[次へ**] をクリックします。

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="images/mdatp-6-systemconfigurationprofiles-2.png" alt-text="カスタム構成プロファイル - 割り当て" lightbox="images/mdatp-6-systemconfigurationprofiles-2.png":::

1. 確認と **作成**。
1. **デバイス** \> **構成プロファイルを** 開くと、作成したプロファイルがそこに表示されます。

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="images/mdatp-6-systemconfigurationprofiles-3.png" alt-text="カスタム構成プロファイルの完了" lightbox="images/mdatp-6-systemconfigurationprofiles-3.png":::

### <a name="approve-system-extensions"></a>システム拡張機能を承認する

このプロファイルは、macOS 10.15 (Catalina) 以降に必要です。 古いmacOSでは無視されます。

1. [構成 **プロファイル]** で [ **プロファイルの作成] を選択します**。
1. **[プラットフォーム**=**macOS****プロファイルの種類** テンプレート] を選択 **します**=。 **テンプレート名**=**拡張機能**。 **[作成]** をクリックします。
1. [ **基本]** タブで、この新しいプロファイルに名前を付けます。
1. [ **構成設定** ] タブの [ **システム拡張機能** ] を展開し、[ **許可されるシステム拡張機能** ] セクションに次のエントリを追加します。

    |バンドル識別子|チーム識別子|
    |---|---|
    |com.microsoft.wdav.epsext|UBF8T346G9|
    |com.microsoft.wdav.netext|UBF8T346G9|

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="images/mac-system-extension-intune2.png" alt-text="システムの拡張機能の設定" lightbox="images/mac-system-extension-intune2.png":::

1. [ **割り当て** ] タブで、このプロファイルを **[すべてのユーザー] & [すべてのデバイス**] に割り当てます。
1. この構成プロファイルを確認して作成します。

### <a name="kernel-extensions"></a>カーネル拡張機能

このプロファイルは、macOS 10.15 (Catalina) 以降に必要です。 新しいmacOSでは無視されます。

> [!CAUTION]
> Apple シリコン (M1) デバイスでは、KEXT はサポートされていません。 これらのデバイスでは、KEXT ポリシーで構成される構成プロファイルのインストールが失敗します。

1. [構成 **プロファイル]** で [ **プロファイルの作成] を選択します**。
1. **[プラットフォーム**=**macOS****プロファイルの種類** テンプレート] を選択 **します**=。 **テンプレート名**=**拡張機能**。 **[作成]** をクリックします。
1. [ **基本]** タブで、この新しいプロファイルに名前を付けます。
1. [ **構成設定** ] タブで、[ **カーネル拡張機能**] を展開します。
1. **チーム識別子** を **UBF8T346G9** に設定し、[**次へ**] をクリックします。

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="images/mac-kernel-extension-intune2.png" alt-text="カーネル拡張機能に使用できるチーム識別子。" lightbox="images/mac-kernel-extension-intune2.png":::

1. [ **割り当て** ] タブで、このプロファイルを **[すべてのユーザー] & [すべてのデバイス**] に割り当てます。
1. この構成プロファイルを確認して作成します。

### <a name="full-disk-access"></a>フル ディスク アクセス

   > [!CAUTION]
   > macOS 10.15 (Catalina) には、新しいセキュリティとプライバシーの強化が含まれています。 このバージョン以降、既定では、アプリケーションは明示的な同意なしにディスク上の特定の場所 (ドキュメント、ダウンロード、デスクトップなど) にアクセスできません。 この同意がない場合、Microsoft Defender for Endpointはデバイスを完全に保護できません。
   >
   > この構成プロファイルは、Microsoft Defender for Endpointへのフル ディスク アクセスを許可します。 以前にIntuneを使用してMicrosoft Defender for Endpointを構成した場合は、この構成プロファイルを使用してデプロイを更新することをお勧めします。

[GitHub リポジトリ](https://github.com/microsoft/mdatp-xplat/tree/master/macos/mobileconfig/profiles)から [**fulldisk.mobileconfig**](https://raw.githubusercontent.com/microsoft/mdatp-xplat/master/macos/mobileconfig/profiles/fulldisk.mobileconfig) をダウンロードします。

"Defender for Endpoint Full Disk Access" をプロファイル名として使用し、**fulldisk.mobileconfig** を構成プロファイル名としてダウンロードして、上から [BLOB をオンボード](#onboarding-blob)する手順に従います。

### <a name="network-filter"></a>ネットワーク フィルター

エンドポイントの検出と応答の機能の一部として、macOSのMicrosoft Defender for Endpointはソケット トラフィックを検査し、この情報をMicrosoft 365 Defender ポータルに報告します。 次のポリシーを使用すると、ネットワーク拡張機能でこの機能を実行できます。

[GitHub リポジトリ](https://github.com/microsoft/mdatp-xplat/tree/master/macos/mobileconfig/profiles)から [**netfilter.mobileconfig**](https://raw.githubusercontent.com/microsoft/mdatp-xplat/master/macos/mobileconfig/profiles/netfilter.mobileconfig) をダウンロードします。

"Defender for Endpoint Network Filter" をプロファイル名として使用し、**netfilter.mobileconfig** を構成プロファイル名としてダウンロードして、上から [BLOB をオンボードする](#onboarding-blob)手順に従います。

### <a name="notifications"></a>通知

このプロファイルは、macOS および Microsoft Auto Update のMicrosoft Defender for Endpointが、macOS 10.15 (Catalina) 以降の UI で通知を表示できるようにするために使用されます。

[GitHub リポジトリ](https://github.com/microsoft/mdatp-xplat/tree/master/macos/mobileconfig/profiles)から [**notif.mobileconfig**](https://raw.githubusercontent.com/microsoft/mdatp-xplat/master/macos/mobileconfig/profiles/notif.mobileconfig) をダウンロードします。

上から [BLOB をオンボードする手順に](#onboarding-blob) 従い、プロファイル名として "Defender for Endpoint Notification" を使用し、 **notif.mobileconfig を** 構成プロファイル名としてダウンロードします。

### <a name="view-status"></a>状態の表示

Intuneの変更が登録済みデバイスに反映されると、[**デバイスの状態** の **監視**\>] に一覧表示されます。

> [!div class="mx-imgBorder"]
> :::image type="content" source="images/mdatp-7-devicestatusblade.png" alt-text="デバイスの状態のビュー" lightbox="images/mdatp-7-devicestatusblade.png":::

## <a name="publish-application"></a>アプリケーションの発行

この手順では、登録されたマシンにMicrosoft Defender for Endpointをデプロイできます。

1. [Microsoft エンドポイント マネージャー管理センター](https://endpoint.microsoft.com/)で、アプリを開 **きます**。

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="images/mdatp-8-app-before.png" alt-text="アプリケーションの概要ページ" lightbox="images/mdatp-8-app-before.png":::

1. [プラットフォーム別] > macOS > [追加] を選択します。
1. [**アプリの種類**=] **を選択macOS**、[**選択**] をクリックします。

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="images/mdatp-9-app-type.png" alt-text="特定のアプリケーションの種類" lightbox="images/mdatp-9-app-type.png":::

1. 既定値のままにして、[ **次へ**] をクリックします。

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="images/mdatp-10-properties.png" alt-text="アプリケーションのプロパティ ページ" lightbox="images/mdatp-10-properties.png":::

1. 割り当てを追加し、[ **次へ**] をクリックします。

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="images/mdatp-11-assignments.png" alt-text="[Intuneの割り当て情報] ページ" lightbox="images/mdatp-11-assignments.png":::

1. 確認と **作成**。
1. **Apps** \> **By platform** \> **macOS** にアクセスすると、すべてのアプリケーションの一覧に表示されます。

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="images/mdatp-12-applications.png" alt-text="アプリケーションの一覧ページ" lightbox="images/mdatp-12-applications.png":::

詳細については、「[Microsoft Intuneを使用してmacOSデバイスにMicrosoft Defender for Endpointを追加する](/mem/intune/apps/apps-advanced-threat-protection-macos)」を参照してください)。

   > [!CAUTION]
   > 上で説明したように、必要なすべての構成プロファイルを作成し、すべてのマシンにプッシュする必要があります。

## <a name="client-device-setup"></a>クライアント デバイスのセットアップ

標準の[ポータル サイトインストール](/intune-user-help/enroll-your-device-in-intune-macos-cp)を超える Mac デバイス用の特別なプロビジョニングは必要ありません。

1. デバイス管理を確認します。

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="images/mdatp-3-confirmdevicemgmt.png" alt-text="[デバイス管理の確認] ページ" lightbox="images/mdatp-3-confirmdevicemgmt.png":::

    [ **システム環境設定を開く] を** 選択し、一覧で **[管理プロファイル** ] を見つけて、[ **承認]...** を選択します。管理プロファイルは **[確認済** み] と表示されます。

    :::image type="content" source="images/mdatp-4-managementprofile.png" alt-text="[管理プロファイル] ページ" lightbox="images/mdatp-4-managementprofile.png":::

2. **[続行]** を選択し、登録を完了します。

   これで、さらに多くのデバイスを登録できます。 システム構成とアプリケーション パッケージのプロビジョニングが完了したら、後で登録することもできます。

3. Intuneで、[**デバイスのすべてのデバイス** の **管理** \> **] を**\>開きます。 ここには、一覧の中からデバイスが表示されます。

   > [!div class="mx-imgBorder"]
   > :::image type="content" source="images/mdatp-5-alldevices.png" alt-text="[すべてのデバイス] ページ" lightbox="images/mdatp-5-alldevices.png":::

## <a name="verify-client-device-state"></a>クライアント デバイスの状態を確認する

1. 構成プロファイルがデバイスに展開されたら、Mac デバイスで **[システム環境設定プロファイル] を**\>開きます。

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="images/mdatp-13-systempreferences.png" alt-text="[システムの基本設定] ページ" lightbox="images/mdatp-13-systempreferences.png":::

   :::image type="content" source="images/mdatp-14-systempreferencesprofiles.png" alt-text="[システム環境設定プロファイル] ページ" lightbox="images/mdatp-14-systempreferencesprofiles.png":::

2. 次の構成プロファイルが存在し、インストールされていることを確認します。 **管理プロファイル** は、Intune システム プロファイルである必要があります。 _Wdav-config_ と _wdav-kext_ は、Intuneで追加されたシステム構成プロファイルです。

   :::image type="content" source="images/mdatp-15-managementprofileconfig.png" alt-text="[プロファイル] ページ" lightbox="images/mdatp-15-managementprofileconfig.png":::

3. 右上隅にMicrosoft Defender for Endpoint アイコンも表示されます。

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="images/mdatp-icon-bar.png" alt-text="ステータス バーのMicrosoft Defender for Endpointのアイコン" lightbox="images/mdatp-icon-bar.png":::

## <a name="troubleshooting"></a>トラブルシューティング

問題: ライセンスが見つかりません。

解決策: 上記の手順に従って、WindowsDefenderATPOnboarding.xmlを使用してデバイス プロファイルを作成します。

## <a name="logging-installation-issues"></a>インストールの問題のログ記録

エラーが発生したときにインストーラーによって作成された自動的に生成されたログを見つける方法の詳細については、「インストールの問題の [ログ記録](mac-resources.md#logging-installation-issues)」を参照してください。

## <a name="uninstallation"></a>アンインストール

クライアント デバイスからmacOSのMicrosoft Defender for Endpointを削除する方法の詳細については、「[アンインストール](mac-resources.md#uninstalling)」を参照してください。
