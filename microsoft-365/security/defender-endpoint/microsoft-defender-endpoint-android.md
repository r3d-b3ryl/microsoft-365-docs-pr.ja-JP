---
title: Android 用 Microsoft Defender for Endpoint
ms.reviewer: ''
description: AndroidにMicrosoft Defender for Endpointをインストールして使用する方法について説明します
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
ms.openlocfilehash: 8de6af6f04243a8481d116fe9a67f5420b536f6c
ms.sourcegitcommit: 133bf9097785309da45df6f374a712a48b33f8e9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/10/2022
ms.locfileid: "66016506"
---
# <a name="microsoft-defender-for-endpoint-on-android"></a>Android 用 Microsoft Defender for Endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

このトピックでは、Androidで Defender for Endpoint をインストール、構成、更新、および使用する方法について説明します。

> [!CAUTION]
> Android上で Defender for Endpoint と共に他のサード パーティのエンドポイント保護製品を実行すると、パフォーマンスの問題と予期しないシステム エラーが発生する可能性があります。

## <a name="how-to-install-microsoft-defender-for-endpoint-on-android"></a>AndroidにMicrosoft Defender for Endpointをインストールする方法

### <a name="prerequisites"></a>前提条件

- **エンド ユーザーの場合**:
  - エンド ユーザーには、Microsoft Intune ライセンスが割り当てられている必要があります。 ライセンスを割り当てる方法の詳細については、「 [ユーザーにライセンスを割り当てる」を](/azure/active-directory/users-groups-roles/licensing-groups-assign)参照してください。
  - アプリのユーザーには、Microsoft Defender for Endpoint ライセンスが割り当てられている必要があります。 ライセンスを割り当てる方法の詳細については、「[Microsoft Defender for Endpointライセンス要件」を](/microsoft-365/security/defender-endpoint/minimum-requirements#licensing-requirements)参照してください。
  - Intune ポータル サイトアプリは[Google Play](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal)からダウンロードでき、Android デバイスで使用できます。
  - さらに、デバイスコンプライアンス ポリシーを適用するために、Intune ポータル サイト アプリを使用してデバイスIntune[登録](/mem/intune/user-help/enroll-device-android-company-portal)できます。 

- **管理者の場合**:
   - Microsoft 365 Defender ポータルへのアクセス。
   - [管理センター Microsoft エンドポイント マネージャー](https://go.microsoft.com/fwlink/?linkid=2109431)アクセスして、次の手順にアクセスします。
     - 組織内の登録済みユーザー グループにアプリをデプロイします。
     - アプリ保護ポリシーでMicrosoft Defender for Endpointリスクシグナルを構成します。
  
    > [!NOTE]
    >
    > - Microsoft Defender for Endpointでは、モバイル デバイス管理 (MDM) を使用して登録されていないが、モバイル アプリケーションの管理にIntuneを使用しているデバイスのマネージド アプリケーション (MAM) 内の組織のデータに対する保護が拡張されるようになりました。 また、モバイル [アプリケーション管理 (MAM)](/mem/intune/apps/mam-faq) にIntuneを引き続き使用しながら、他のエンタープライズ モビリティ管理ソリューションを使用するお客様にもこのサポートを拡張します。
    > - さらに、Microsoft Defender for Endpointでは、モバイル デバイス管理 (MDM) を使用して登録されているデバイスIntune既にサポートされています。

### <a name="network-requirements"></a>ネットワーク要件

- ネットワークに接続されているときにAndroidのMicrosoft Defender for Endpointを機能させるには、ファイアウォール/プロキシを構成して[、Microsoft Defender for Endpointサービス URL へのアクセスを有効にする](configure-proxy-internet.md#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server)必要があります。

### <a name="system-requirements"></a>システム要件

- Android 6.0 以降を実行している携帯電話。 **Androidを実行している携帯電話、タブレット、Androidを実行しているその他のモバイル デバイスは現在サポートされていません。**
- Intune ポータル サイトアプリは[Google Play](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal)からダウンロードされ、インストールされます。 デバイス コンプライアンス ポリシーを適用するには、Intuneデバイス登録が必要です。

### <a name="installation-instructions"></a>インストール手順

AndroidのMicrosoft Defender for Endpointは、登録済みデバイスの両方のモード (レガシ デバイス管理者モードとAndroid Enterprise モード) へのインストールをサポートします。 **現在、仕事用プロファイルを持つ個人所有のデバイスと会社所有のフル マネージド ユーザー デバイスの登録は、Android Enterpriseでサポートされています。準備ができたら、他のAndroid Enterprise モードのサポートが発表されます。**

- AndroidでのMicrosoft Defender for Endpointのデプロイは、Microsoft Intune (MDM) を介して行われます。 詳細については、「[Microsoft Intuneを使用してAndroidにMicrosoft Defender for Endpointをデプロイする」を参照](android-intune.md)してください。
- モバイル デバイス管理 (MDM) を使用して登録されていないデバイスへの Intune Microsoft Defender for Endpointのインストールについては、「[アプリ保護ポリシー (MAM) でMicrosoft Defender for Endpointリスクシグナルを構成する](android-configure-mam.md)」を参照してください。

> [!NOTE]
> **AndroidのMicrosoft Defender for Endpointは、現在 [Google Play](https://play.google.com/store/apps/details?id=com.microsoft.scmx)で利用できます。**
>
> IntuneからGoogle Playに接続して、デバイス管理者モードとAndroid Enterpriseエントロール モードMicrosoft Defender for Endpointアプリを展開できます。

## <a name="how-to-configure-microsoft-defender-for-endpoint-on-android"></a>AndroidでMicrosoft Defender for Endpointを構成する方法

Android機能でMicrosoft Defender for Endpointを構成する方法に関するガイダンスについては、「Android機能[のMicrosoft Defender for Endpointを構成する」を](android-configure.md)参照してください。

## <a name="related-topics"></a>関連トピック

- [Microsoft Intune を使用した Android 用 Microsoft Defender for Endpoint の展開](android-intune.md)
- [Android 機能用に Microsoft Defender for Endpoint を構成する](android-configure.md)
- [モバイル アプリケーション管理 (MAM) の基本](/mem/intune/apps/app-management#mobile-application-management-mam-basics)
