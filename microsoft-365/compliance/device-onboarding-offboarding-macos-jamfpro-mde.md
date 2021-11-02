---
title: Microsoft Defender for Endpoint のお客様向け JAMF Proを使用したコンプライアンス ソリューションへのオンボードおよびオフボード macOS デバイス (プレビュー)
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
description: MICROSOFT Defender for Endpoint のお客様向け JAMF Microsoft 365を使用して、macOS デバイスをオンボードおよびオフボードProコンプライアンス ソリューションに組み込む方法について説明します (プレビュー)
ms.openlocfilehash: dd5bedb473de6fa608d1e28ad7a81c3a6d7d5b30
ms.sourcegitcommit: bf3965b46487f6f8cf900dd9a3af8b213a405989
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/02/2021
ms.locfileid: "60648200"
---
# <a name="onboard-and-offboard-macos-devices-into-compliance-solutions-using-jamf-pro-for-microsoft-defender-for-endpoint-customers-preview"></a>Microsoft Defender for Endpoint のお客様向け JAMF Proを使用したコンプライアンス ソリューションへのオンボードおよびオフボード macOS デバイス (プレビュー)

JAMF を使用して、Proコンプライアンス ソリューションに macOS デバイスMicrosoft 365できます。

> [!IMPORTANT]
> Microsoft Defender  for Endpoint (MDE) を macOS デバイスに展開している場合は、次の手順を実行します。

## <a name="get-registered"></a>登録を取得する

この機能にアクセスするには、テナントを Microsoft に登録する必要があります。 macOS[のサポートに登録Microsoft 365を参照してください](https://aka.ms/Ignite2021DLP)。

**適用対象:**

- MDE を macOS デバイスに展開しているお客様。
- [Microsoft 365エンドポイント データ損失防止 (DLP)](./endpoint-dlp-learn-about.md)
- [インサイダー リスクの管理](insider-risk-management.md#learn-about-insider-risk-management-in-microsoft-365)


## <a name="before-you-begin"></a>はじめに

- [macOS デバイスが参加Azure ADする](https://docs.jamf.com/10.30.0/jamf-pro/administrator-guide/Azure_AD_Integration.html)
- macOS デバイスが JAMF pro [を介して管理されている必要があります。](https://www.jamf.com/resources/product-documentation/jamf-pro-installation-guide-for-mac/) 
- macOS デバイスに v95+ Edge ブラウザーをインストールする 

## <a name="onboard-devices-into-microsoft-365-compliance-solutions-using-jamf-pro"></a>JAMF を使用してMicrosoft 365コンプライアンス ソリューションにデバイスをオンボードPro

コンプライアンス ソリューションへの macOS デバイスのオンボードは、複数フェーズのプロセスです。

### <a name="download-the-configuration-files"></a>構成ファイルをダウンロードする

1. この手順では、これらのファイルが必要です。

|に必要なファイル |source |
|---------|---------|
|アクセシビリティ |[アクセシビリティ.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/profiles/accessibility.mobileconfig)|
フル ディスク アクセス     |[fulldisk.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/profiles/fulldisk.mobileconfig)|
|MDE の基本設定 |[schema.json](https://github.com/microsoft/mdatp-xplat/blob/master/macos/schema/schema.json)

> [!TIP]
> *.mobileconfig* ファイルは、個別にダウンロードするか、以下を含 [む単一の結合ファイル](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/combined/mdatp-nokext.mobileconfig)でダウンロードできます。
> - アクセシビリティ.mobileconfig
> - fulldisk.mobileconfig
>
>これらの個々のファイルが更新された場合は、結合されたファイルを再度ダウンロードするか、単一の更新されたファイルを個別にダウンロードする必要があります。

### <a name="update-the-existing-mde-preference-domain-profile-using-the-jamf-pro-console"></a>JAMF PRO コンソールを使用して既存の MDE Preference ドメイン プロファイルを更新する

1. ダウンロードしたschema.xml **schema.json ファイルを使用して、ユーザー プロファイル** を更新します。

1. **[MDE 基本設定ドメインのプロパティ] で、** 次の設定を選択します。
    - 機能 
        - システム拡張機能の使用: `enabled` - Catalina のネットワーク拡張機能に必要
        - データ損失防止の使用: `enabled`

1. [スコープ] **タブを選択** します。

1. この構成プロファイルを展開するグループを選択します。

1. **[保存]** を選択します。 

### <a name="update-the-configuration-profile-for-grant-full-disk-access"></a>[ディスクへのフル アクセスを許可する] の構成プロファイルを更新する

1. **fulldisk.mobileconfig** ファイルを使用して、既存のフル ディスク アクセス プロファイルを更新します。

1. **アップロードdisk.mobileconfig ファイルを** JAMF に移動します。 [「JAMF を使用したカスタム構成プロファイルの展開」を参照Pro。](https://docs.jamf.com/technical-articles/Deploying_Custom_Configuration_Profiles_Using_Jamf_Pro.html)

### <a name="grant-accessibility-access-to-dlp"></a>DLP へのアクセシビリティ アクセスを許可する

1. 以前にダウンロードしたアクセシビリティ.mobileconfig ファイルを使用します。

1. アップロードを使用したカスタム構成プロファイルの展開」の説明に従って[JAMF](https://www.jamf.com/jamf-nation/articles/648/deploying-custom-configuration-profiles-using-jamf-pro)にPro。

### <a name="check-the-macos-device"></a>macOS デバイスを確認する 

1. macOS デバイスを再起動します。

1. [**システム設定プロファイル]**  >  **を開きます**。

1. 次の情報が表示されます。
    - アクセシブル
    - フル ディスク アクセス
    - カーネル拡張機能プロファイル
    - MAU
    - MDATP オンボーディング
    - MDE の基本設定
    - 管理プロファイル
    - ネットワーク フィルター
    - 通知
    - システム拡張プロファイル

## <a name="offboard-macos-devices-using-jamf-pro"></a>JAMF デバイスを使用するオフボード macOS Pro

> [!IMPORTANT]
> Offboarding を使用すると、デバイスはポータルへのセンサー データの送信を停止しますが、デバイスからのデータ (通知への参照を含む) は最大 6 か月間保持されます。

macOS デバイスをオフボードするには、次の手順を実行します。

 1. **[MDE 基本設定ドメインのプロパティ] で**、これらの設定の値を削除します。
    - 機能 
        - システム拡張機能の使用
        - データ損失防止の使用

1. [**保存**] を選択します。
