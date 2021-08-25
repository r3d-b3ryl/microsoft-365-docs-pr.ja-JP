---
title: Android 用 Microsoft Defender for Endpoint
ms.reviewer: ''
description: Android に Microsoft Defender for Endpoint をインストールして使用する方法について説明します。
keywords: microsoft、 defender、 Microsoft Defender for Endpoint, android, installation, deploy, uninstallation, intune
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 1e16b6aeb664c69c419337b82081a85f10344fba
ms.sourcegitcommit: f358e321f7e81eff425fe0f0db1be0f3348d2585
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/24/2021
ms.locfileid: "58507928"
---
# <a name="microsoft-defender-for-endpoint-on-android"></a>Android 用 Microsoft Defender for Endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

このトピックでは、Android 上で Defender for Endpoint をインストール、構成、更新、および使用する方法について説明します。

> [!CAUTION]
> Android で Defender for Endpoint と共に他のサード パーティ製のエンドポイント保護製品を実行すると、パフォーマンスの問題や予期しないシステム エラーが発生する可能性があります。

## <a name="how-to-install-microsoft-defender-for-endpoint-on-android"></a>Android に Microsoft Defender for Endpoint をインストールする方法

### <a name="prerequisites"></a>前提条件

- **エンド ユーザーの場合**:
  - アプリのエンド ユーザーに割り当てられた Microsoft Defender for Endpoint ライセンス。 [「Microsoft Defender for Endpoint ライセンス要件」を参照してください。](/microsoft-365/security/defender-endpoint/minimum-requirements#licensing-requirements)
  - Intune ポータル サイトは Google Play からダウンロード[可能](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal)で、Android デバイスで利用できます。
  - さらに、Intune デバイスコンプライアンス ポリシーを[](/mem/intune/user-help/enroll-device-android-company-portal)適用するために、Intune ポータル サイトアプリを介してデバイスを登録できます。 これには、エンド ユーザーにライセンスを割り当てるMicrosoft Intune必要があります。
  - ライセンスを割り当てる方法の詳細については、「ユーザーにライセンスを割り当 [てる」を参照してください](/azure/active-directory/users-groups-roles/licensing-groups-assign)。

- **管理者向け**
  - ポータルへのアクセスMicrosoft 365 Defenderします。

    > [!NOTE]
    > Microsoft Intuneは、Android に Microsoft Defender for Endpoint を展開する場合にサポートされている唯一のモバイル デバイス管理 (MDM) ソリューションです。 現在、Intune で Android 関連のデバイス コンプライアンス ポリシーで Defender for Endpoint を適用する場合は、現在登録されているデバイスだけがサポートされています。

  - 管理[Microsoft エンドポイント マネージャーアクセスして](https://go.microsoft.com/fwlink/?linkid=2109431)、組織の登録済みユーザー グループにアプリを展開します。
    - ポータルへのアクセスMicrosoft 365 Defenderします。

        > [!NOTE]
        > Microsoft Defender for Endpoint では、モバイル デバイス管理 (MDM) を使用していないが、Intune を使用してモバイル アプリケーションを管理しているユーザーの管理アプリケーション内の組織のデータに保護を拡張できます。 また、このサポートは、他のエンタープライズ モビリティ管理ソリューションを使用しているお客様にも拡張しますが、モバイル アプリケーション管理 [(MAM)](/mem/intune/apps/mam-faq)には Intune を使用します。
        >
        > この更新プログラムの前に、Microsoft Defender for Endpoint は Intune MDM のみを使用して登録されたデバイスで作業しました。

    - 管理[Microsoft エンドポイント マネージャーアクセスして](https://go.microsoft.com/fwlink/?linkid=2109431)、組織の登録済みユーザー グループにアプリを展開します。

### <a name="network-requirements"></a>ネットワーク要件

- Microsoft Defender for Endpoint on Android がネットワークに接続されている場合に機能するには [、Microsoft Defender for Endpoint](configure-proxy-internet.md#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server)サービス URL へのアクセスを有効にするようにファイアウォール/プロキシを構成する必要があります。

### <a name="system-requirements"></a>システム要件

- Android 6.0 以上を実行している携帯電話。 **Android を実行しているタブレットや他のモバイル デバイスは現在サポートされていません。**
- Intune ポータル サイトは Google Play から[ダウンロードされ、](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal)インストールされます。 Intune デバイス コンプライアンス ポリシーを適用するには、デバイスの登録が必要です。

### <a name="installation-instructions"></a>インストール手順

Android 上の Microsoft Defender for Endpoint は、登録されているデバイスの両方のモード (従来のデバイス管理者モードと Android デバイス モード) へのインストールEnterpriseサポートしています。 **現在、仕事用プロファイルと企業所有の完全に管理されたユーザー デバイス登録を持つ個人所有のデバイスは、Android Enterprise でサポートされています。他の Android Enterpriseのサポートは、準備ができたら発表されます。**

Android での Microsoft Defender for Endpoint の展開は、Microsoft Intune (MDM) 経由です。 詳細については、「Deploy Microsoft Defender for Endpoint on Android with Microsoft Intune」[を参照してください](android-intune.md)。

> [!NOTE]
> **Android 上のエンドポイント用 Microsoft Defender は [、Google Play で利用](https://play.google.com/store/apps/details?id=com.microsoft.scmx) できます。**
>
> Intune から Google Play に接続して、Microsoft Defender for Endpoint アプリを展開し、デバイス管理者モードと Android デバイス Enterprise展開できます。

## <a name="how-to-configure-microsoft-defender-for-endpoint-on-android"></a>Android 上のエンドポイント用 Microsoft Defender を構成する方法

Android の機能で Microsoft Defender for Endpoint を構成する方法については、「Configure Microsoft Defender for Endpoint on Android フィーチャー [」を参照してください](android-configure.md)。

## <a name="related-topics"></a>関連項目

- [Microsoft Intune を使用した Android 用 Microsoft Defender for Endpoint の展開](android-intune.md)
- [Android 機能用に Microsoft Defender for Endpoint を構成する](android-configure.md)
- [モバイル アプリケーション管理 (MAM) の基本](/mem/intune/apps/app-management#mobile-application-management-mam-basics)
