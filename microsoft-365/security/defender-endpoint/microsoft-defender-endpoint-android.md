---
title: Android 用 Microsoft Defender for Endpoint
ms.reviewer: ''
description: Android でMicrosoft Defender for Endpointをインストールして使用する方法について説明します
keywords: microsoft, defender, Microsoft Defender for Endpoint, android, インストール, デプロイ, アンインストール, intune
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
- m365-initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 51f4915da08920018526ac7eb17372247e28de6d
ms.sourcegitcommit: 292de1a7e5ecc2e9e6187126aebba6d3b9416dff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/06/2022
ms.locfileid: "65243098"
---
# <a name="microsoft-defender-for-endpoint-on-android"></a>Android 用 Microsoft Defender for Endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

このトピックでは、Android 上で Defender for Endpoint をインストール、構成、更新、および使用する方法について説明します。

> [!CAUTION]
> Android 上で Defender for Endpoint と共に他のサード パーティのエンドポイント保護製品を実行すると、パフォーマンスの問題と予期しないシステム エラーが発生する可能性があります。

## <a name="how-to-install-microsoft-defender-for-endpoint-on-android"></a>Android にMicrosoft Defender for Endpointをインストールする方法

### <a name="prerequisites"></a>前提条件

- **エンド ユーザーの場合**:
  - Microsoft Defender for Endpointアプリのエンド ユーザーに割り当てられたライセンス。 [ライセンス要件Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/minimum-requirements#licensing-requirements)参照してください。
  - Android デバイスをオンボードする前に、Intuneライセンスが必要です。
  - Intune ポータル サイトアプリは [Google Play](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) からダウンロードでき、Android デバイスで利用できます。
  - さらに、デバイスコンプライアンス ポリシーを適用するために、Intune ポータル サイト アプリを使用してデバイスIntune[登録](/mem/intune/user-help/enroll-device-android-company-portal)できます。 これには、エンド ユーザーにMicrosoft Intuneライセンスを割り当てる必要があります。
  - ライセンスを割り当てる方法の詳細については、「 [ユーザーにライセンスを割り当てる」を](/azure/active-directory/users-groups-roles/licensing-groups-assign)参照してください。

- **管理者向け**
   - Microsoft 365 Defender ポータルへのアクセス。
   - [管理センター Microsoft エンドポイント マネージャー](https://go.microsoft.com/fwlink/?linkid=2109431)アクセスして、
       - 組織内の登録済みユーザー グループにアプリをデプロイします。
       - アプリ保護ポリシーでMicrosoft Defender for Endpointリスクシグナルを構成します。
  
    > [!NOTE]
    > - Microsoft Defender for Endpointでは、モバイル デバイス管理 (MDM) を使用して登録されていないが、モバイル アプリケーションの管理にIntuneを使用しているデバイスのマネージド アプリケーション (MAM) 内の組織のデータに対する保護が拡張されるようになりました。 また、モバイル [アプリケーション管理 (MAM)](/mem/intune/apps/mam-faq) にIntuneを引き続き使用しながら、他のエンタープライズ モビリティ管理ソリューションを使用するお客様にもこのサポートを拡張します。
    > - さらに、Microsoft Defender for Endpointでは、モバイル デバイス管理 (MDM) を使用して登録されているデバイスIntune既にサポートされています。


### <a name="network-requirements"></a>ネットワーク要件

- ネットワークに接続されているときに Android のMicrosoft Defender for Endpointを機能させるには、ファイアウォール/プロキシを構成して[、Microsoft Defender for Endpointサービス URL へのアクセスを有効にする](configure-proxy-internet.md#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server)必要があります。

### <a name="system-requirements"></a>システム要件

- Android 6.0 以降を実行している携帯電話。 **Android Go を実行している携帯電話、タブレット、Android を実行しているその他のモバイル デバイスは、現在サポートされていません。**
- Intune ポータル サイトアプリは [Google Play](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) からダウンロードされ、インストールされます。 デバイス コンプライアンス ポリシーを適用するには、Intuneデバイス登録が必要です。

### <a name="installation-instructions"></a>インストール手順

Android のMicrosoft Defender for Endpointでは、登録済みデバイスの両方のモード (従来のデバイス管理者モードと Android Enterprise モード) へのインストールがサポートされます。 **現在、仕事用プロファイルを持つ個人所有のデバイスと企業所有のフル マネージド ユーザー デバイス登録は、Android Enterpriseでサポートされています。その他の Android Enterprise モードのサポートは、準備ができたらお知らせします。**

- Android でのMicrosoft Defender for Endpointのデプロイは、Microsoft Intune (MDM) を介して行われます。 詳細については、「[Microsoft Intuneを使用して Android にMicrosoft Defender for Endpointをデプロイする](android-intune.md)」を参照してください。
- モバイル デバイス管理 (MDM) を使用して登録されていないデバイスへの Intune Microsoft Defender for Endpointのインストールについては、「[アプリ保護ポリシー (MAM) でMicrosoft Defender for Endpointリスクシグナルを構成する](android-configure-mam.md)」を参照してください。

> [!NOTE]
> **Android のMicrosoft Defender for Endpointは、[Google Play](https://play.google.com/store/apps/details?id=com.microsoft.scmx) で利用できるようになりました。**
>
> Intuneから Google Play に接続して、デバイス管理者モードと Android Enterpriseエントロール モード間で、Microsoft Defender for Endpoint アプリをデプロイできます。

## <a name="how-to-configure-microsoft-defender-for-endpoint-on-android"></a>Android でMicrosoft Defender for Endpointを構成する方法

Android 機能でMicrosoft Defender for Endpointを構成する方法に関するガイダンスについては、「Android 機能での[Microsoft Defender for Endpointの構成」を](android-configure.md)参照してください。

## <a name="related-topics"></a>関連項目

- [Microsoft Intune を使用した Android 用 Microsoft Defender for Endpoint の展開](android-intune.md)
- [Android 機能用に Microsoft Defender for Endpoint を構成する](android-configure.md)
- [モバイル アプリケーション管理 (MAM) の基本](/mem/intune/apps/app-management#mobile-application-management-mam-basics)
