---
title: Microsoft Defender for Endpoint のお客様向け JAMF Pro を使用したコンプライアンス ソリューションへの macOS デバイスのオンボードとオフボード
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
description: Microsoft Defender for Endpointのお客様向けに JAMF Pro を使用して macOS デバイスを Microsoft Purview ソリューションにオンボードおよびオフボードする方法について説明します
ms.openlocfilehash: 97ab1dbccc28cd1f9d14635c2fa351d0295202c1
ms.sourcegitcommit: c29fc9d7477c3985d02d7a956a9f4b311c4d9c76
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/06/2022
ms.locfileid: "66622923"
---
# <a name="onboard-and-offboard-macos-devices-into-compliance-solutions-using-jamf-pro-for-microsoft-defender-for-endpoint-customers"></a>Microsoft Defender for Endpoint のお客様向け JAMF Pro を使用したコンプライアンス ソリューションへの macOS デバイスのオンボードとオフボード

JAMF Pro を使用して、MacOS デバイスを Microsoft Purview ソリューションにオンボードできます。

> [!IMPORTANT]
> macOS デバイスに Microsoft Defender for Endpoint (MDE) を展開している ***場合は***、次の手順を使用します。

**適用対象:**

- MACOS デバイスに MDE を展開しているお客様。
- [エンドポイントのデータ損失防止](./endpoint-dlp-learn-about.md)
- [インサイダー リスク管理](insider-risk-management.md)


## <a name="before-you-begin"></a>はじめに

- [MACOS デバイスが JAMF pro を介して管理され、JAMF](https://www.jamf.com/resources/product-documentation/jamf-pro-installation-guide-for-mac/) Connect またはIntuneを介して ID (Azure AD joined UPN) に関連付けられていることを確認します。
- macOS デバイスに v95+ Edge ブラウザーをインストールする

## <a name="onboard-devices-into-microsoft-purview-solutions-using-jamf-pro"></a>JAMF Pro を使用してデバイスを Microsoft Purview ソリューションにオンボードする

macOS デバイスをコンプライアンス ソリューションにオンボードすることは、多段階プロセスです。

### <a name="download-the-configuration-files"></a>構成ファイルをダウンロードする

1. この手順では、これらのファイルが必要です。

|に必要なファイル |source |
|---------|---------|
|アクセシビリティ |[accessibility.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/profiles/accessibility.mobileconfig)|
フル ディスク アクセス     |[fulldisk.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/profiles/fulldisk.mobileconfig)|
|MDE の基本設定 |[schema.json](https://github.com/microsoft/mdatp-xplat/blob/master/macos/schema/schema.json)

> [!TIP]
> *.mobileconfig* ファイルは、個別にダウンロードすることも、次を含む [単一の結合ファイル](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/combined/mdatp-nokext.mobileconfig)でダウンロードすることもできます。
> - accessibility.mobileconfig
> - fulldisk.mobileconfig
>
>これらの個々のファイルのいずれかが更新された場合は、結合されたファイルを再度ダウンロードするか、1 つの更新されたファイルを個別にダウンロードする必要があります。

### <a name="update-the-existing-mde-preference-domain-profile-using-the-jamf-pro-console"></a>JAMF PRO コンソールを使用して既存の MDE 基本設定ドメイン プロファイルを更新する

1. ダウンロードした **schema.json** ファイルを使用して、schema.xml プロファイルを更新します。

1. **[MDE 基本設定ドメインのプロパティ] で** これらの設定を選択します
    - 機能 
        - システム拡張機能を使用する: `enabled` - Catalina のネットワーク拡張機能に必要です
        - データ損失防止を使用する: `enabled`

1. [ **スコープ** ] タブを選択します。

1. この構成プロファイルをデプロイするグループを選択します。

1. **[保存]** を選択します。 

### <a name="update-the-configuration-profile-for-grant-full-disk-access"></a>フル ディスク アクセスを許可する構成プロファイルを更新する

1. **fulldisk.mobileconfig** ファイルを使用して、既存のフル ディスク アクセス プロファイルを更新します。

1. **fulldisk.mobileconfig** ファイルを JAMF にアップロードします。 [JAMF Pro を使用したカスタム構成プロファイルのデプロイに関する説明](https://docs.jamf.com/technical-articles/Deploying_Custom_Configuration_Profiles_Using_Jamf_Pro.html)を参照してください。

### <a name="grant-accessibility-access-to-dlp"></a>DLP へのアクセシビリティ アクセスを付与する

1. 以前にダウンロードした accessibility.mobileconfig ファイルを使用します。

1. [Jamf Pro を使用したカスタム構成プロファイルのデプロイ](https://www.jamf.com/jamf-nation/articles/648/deploying-custom-configuration-profiles-using-jamf-pro)の説明に従って JAMF にアップロードします。

### <a name="check-the-macos-device"></a>macOS デバイスを確認する 

1. macOS デバイスを再起動します。

1. **システム環境設定プロファイルを** > 開 **きます**。

1. 次の情報が表示されます。
    - アクセシビリティ
    - フル ディスク アクセス
    - カーネル拡張機能プロファイル
    - マウ
    - MDATP オンボード
    - MDE 環境設定
    - 管理プロファイル
    - ネットワーク フィルター
    - 通知
    - システム拡張機能プロファイル

## <a name="offboard-macos-devices-using-jamf-pro"></a>JAMF Pro を使用したオフボード macOS デバイス

> [!IMPORTANT]
> オフボーディングにより、デバイスはポータルへのセンサー データの送信を停止しますが、デバイスからのデータ (発生したアラートへの参照を含む) は、最大 6 か月間保持されます。

macOS デバイスをオフボードするには、次の手順に従います。

 1. **[MDE 基本設定ドメインのプロパティ] で**、これらの設定の値を削除します
    - 機能 
        - システム拡張機能を使用する
        - データ損失防止を使用する

1. [**保存**] を選択します。
