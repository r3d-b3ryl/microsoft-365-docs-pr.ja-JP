---
title: Android 用 Microsoft Defender ATP
ms.reviewer: ''
description: Android 用 Microsoft Defender ATP をインストールして使用する方法について説明します。
keywords: microsoft、Defender、atp、android、インストール、展開、アンインストール、intune
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
ms.openlocfilehash: 6518b86861fd5d03533bb787d4ee005d7ace1a0c
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51068828"
---
# <a name="microsoft-defender-for-endpoint-for-android"></a>Android 用エンドポイント用 Microsoft Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Microsoft Defender for Endpoint を体験してみませんか? [無料試用版にサインアップします。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

このトピックでは、Android 用 Defender for Endpoint をインストール、構成、更新、および使用する方法について説明します。

> [!CAUTION]
> Android 用 Defender for Endpoint と共に他のサード パーティ製のエンドポイント保護製品を実行すると、パフォーマンスの問題や予期しないシステム エラーが発生する可能性があります。


## <a name="how-to-install-microsoft-defender-for-endpoint-for-android"></a>Android 用エンドポイント用 Microsoft Defender をインストールする方法

### <a name="prerequisites"></a>前提条件

-   **エンド ユーザー向け**

    -   アプリのエンド ユーザーに割り当てられた Microsoft Defender for Endpoint ライセンス。 [「Microsoft Defender for Endpoint ライセンス要件」を参照してください。](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/minimum-requirements#licensing-requirements)

    -   Intune ポータル サイト アプリは Google Play から [ダウンロードできます。Android](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) デバイスで利用できます。

        -   さらに、Intune ポータル サイト アプリ[](https://docs.microsoft.com/mem/intune/user-help/enroll-device-android-company-portal)を介してデバイスを登録して、Intune デバイスコンプライアンス ポリシーを適用することもできます。 これには、エンド ユーザーに Microsoft Intune ライセンスが割り当てられている必要があります。

    -   ライセンスを割り当てる方法の詳細については、「ユーザーにライセンスを割り当 [てる」を参照してください](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign)。
        

-   **管理者向け**

    -   Microsoft Defender セキュリティ センター ポータルへのアクセス。

        > [!NOTE]
        > Microsoft Intune は、Android 用 Microsoft Defender for Endpoint を展開する唯一のサポートされるモバイル デバイス管理 (MDM) ソリューションです。 現在、Intune で Defender for Endpoint for Android 関連のデバイス コンプライアンス ポリシーを適用するには、現在登録されているデバイスだけがサポートされています。 

    -   Microsoft [Endpoint Manager 管理センターにアクセスして](https://go.microsoft.com/fwlink/?linkid=2109431)、組織内の登録済みユーザー グループにアプリを展開します。

### <a name="system-requirements"></a>システム要件

-   Android 6.0 以上を実行している Android デバイス。
-   Intune ポータル サイト アプリは [、Google Play からダウンロードして](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) インストールされます。 Intune デバイス コンプライアンス ポリシーを適用するには、デバイスの登録が必要です。

### <a name="installation-instructions"></a>インストール手順

Microsoft Defender for Endpoint for Android では、登録済みデバイスの両方のモード (従来のデバイス管理者モードと Android Enterprise モード) へのインストールがサポートされています。
**現在、Android Enterprise では、仕事用プロファイルと企業所有の完全管理ユーザー デバイス登録を持つ個人所有のデバイスがサポートされています。準備ができたら、他の Android Enterprise モードのサポートが発表されます。**

Android 用の Microsoft Defender for Endpoint の展開は、Microsoft Intune (MDM) を介して行います。
詳細については [、「Deploy Microsoft Defender for Endpoint for Android with Microsoft Intune」を参照してください](android-intune.md)。


> [!NOTE]
> **Microsoft Defender for Endpoint for Android は [Google Play で利用](https://play.google.com/store/apps/details?id=com.microsoft.scmx) できます。** <br> Intune から Google Play に接続して、デバイス管理者モードと Android Enterprise entrollment モード全体で Microsoft Defender for Endpoint アプリを展開できます。 

## <a name="how-to-configure-microsoft-defender-for-endpoint-for-android"></a>Android 用エンドポイント用 Microsoft Defender を構成する方法

Microsoft Defender for Endpoint for Android の機能を構成する方法については、「Configure Microsoft Defender for Endpoint for Android フィーチャー」 [を参照してください](android-configure.md)。



## <a name="related-topics"></a>関連項目
- [Microsoft Intune を使用して Microsoft Defender for Endpoint を展開する](android-intune.md)
- [Android の機能用に Microsoft Defender for Endpoint を構成する](android-configure.md)

