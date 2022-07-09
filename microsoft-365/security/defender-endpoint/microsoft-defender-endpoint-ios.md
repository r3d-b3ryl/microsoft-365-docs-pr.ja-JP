---
title: iOS 用 Microsoft Defender for Endpoint API
ms.reviewer: ''
description: iOS にMicrosoft Defender for Endpointをインストールして使用する方法について説明します
keywords: microsoft, defender, Microsoft Defender for Endpoint, ios, 概要, インストール, デプロイ, アンインストール, intune
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365-initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: ac2c34359686da45998fab1076b7501357651318
ms.sourcegitcommit: 2aa5c026cc06ed39a9c1c2bcabd1f563bf5a1859
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/09/2022
ms.locfileid: "66695881"
---
# <a name="microsoft-defender-for-endpoint-on-ios"></a>iOS 用 Microsoft Defender for Endpoint API

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

**iOS のMicrosoft Defender for Endpoint** は、Web サイト、電子メール、アプリからのフィッシングや安全でないネットワーク接続に対する保護を提供します。 すべてのアラートは、Microsoft 365 Defender ポータルの 1 つのウィンドウから利用できます。 このポータルを使用すると、セキュリティ チームは、他のプラットフォームと共に iOS デバイス上の脅威を一元的に表示できます。

> [!CAUTION]
> iOS 上で Defender for Endpoint と共に他のサード パーティのエンドポイント保護製品を実行すると、パフォーマンスの問題と予期しないシステム エラーが発生する可能性があります。

## <a name="prerequisites"></a>前提条件

**エンド ユーザーの場合**

- Microsoft Defender for Endpointアプリのエンド ユーザーに割り当てられたライセンス。 [ライセンス要件Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/minimum-requirements#licensing-requirements)参照してください。

- **登録済みデバイスの場合**:
    - デバイスは、Intuneデバイス コンプライアンス ポリシーを適用するために、Intune ポータル サイト アプリを介して[登録されます](/mem/intune/user-help/enroll-your-device-in-intune-ios)。 これには、エンド ユーザーにMicrosoft Intuneライセンスを割り当てる必要があります。
    - Intune ポータル サイトアプリは [Apple App Store](https://apps.apple.com/us/app/intune-company-portal/id719171358)からダウンロードできます。
    
    >[!NOTE]
    >Apple では、リダイレクトユーザーがアプリ ストアから他のアプリをダウンロードすることは許可されていないため、この手順はユーザーがアプリにオンボードする前に行う必要Microsoft Defender for Endpoint。


    - デバイスは Azure Active Directory に登録されます。 これには、エンド ユーザーが [Microsoft Authenticator アプリ](https://apps.apple.com/app/microsoft-authenticator/id983156458)を使用してサインインする必要があります。

- **登録されていないデバイスの場合**:デバイスは Azure Active Directory に登録されます。 これには、エンド ユーザーが [Microsoft Authenticator アプリ](https://apps.apple.com/app/microsoft-authenticator/id983156458)を使用してサインインする必要があります。

- ライセンスを割り当てる方法の詳細については、「 [ユーザーにライセンスを割り当てる」を](/azure/active-directory/users-groups-roles/licensing-groups-assign)参照してください。

**管理者向け**

- Microsoft 365 Defender ポータルへのアクセス。

- [Microsoft エンドポイント マネージャー管理センター](https://go.microsoft.com/fwlink/?linkid=2109431)にアクセスして、次の情報にアクセスします。
   - 組織内の登録済みユーザー グループにアプリをデプロイします。
   - アプリ保護ポリシー (MAM) でMicrosoft Defender for Endpointリスクシグナルを構成する


    > [!NOTE]
    > - Microsoft Defender for Endpointモバイル デバイス管理 (MDM) を使用していないが、モバイル アプリケーションの管理にIntuneを使用しているユーザーに対して、マネージド アプリケーション内の組織のデータに対する保護を拡張するようになりました。 また、モバイル [アプリケーション管理 (MAM)](/mem/intune/apps/mam-faq) にIntuneを引き続き使用しながら、他のエンタープライズ モビリティ管理ソリューションを使用するお客様にもこのサポートを拡張します。
    > - さらに、Microsoft Defender for Endpointでは、モバイル デバイス管理 (MDM) を使用して登録されているデバイスIntune既にサポートされています。  

**システム要件**

- iOS 12.0 以降を実行している iOS デバイス。 iPad もサポートされています。 *2022 年 3 月 31 日から 3 月 31 日以降、Microsoft Defender for Endpointでサポートされる iOS の最小バージョンは iOS 13.0 になります。*

- デバイスは[、Intune ポータル サイト アプリ](https://apps.apple.com/us/app/intune-company-portal/id719171358)に登録されているか、同じアカウントで [Microsoft Authenticator](https://apps.apple.com/app/microsoft-authenticator/id983156458) を介して Azure Active Directory に登録されています。

 > [!NOTE]
 > iOS ユーザー登録を使用している間、iOS でのMicrosoft Defender for Endpointは現在サポートされていません。

## <a name="installation-instructions"></a>インストール手順

iOS でのMicrosoft Defender for Endpointの展開は、Microsoft エンドポイント マネージャー (MEM) を使用して行うことができます。監視対象デバイスと教師なしデバイスの両方がサポートされています。 エンド ユーザーは [、Apple アプリ ストア](https://aka.ms/mdatpiosappstore)からアプリを直接インストールすることもできます。

- Microsoft エンドポイント マネージャーまたはIntuneを介して登録済みデバイスに展開する方法については、「[iOS でのMicrosoft Defender for Endpointの展開](ios-install.md)」を参照してください。
- アプリ保護ポリシー (MAM) で Defender for Endpoint を使用する方法については、「[Defender for Endpoint リスクシグナル (MAM) を含めるアプリ保護ポリシーを構成する」](ios-install-unmanaged.md)を参照してください。

## <a name="resources"></a>リソース

- 今後のリリースについては、iOS または[ブログ](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/bg-p/MicrosoftDefenderATPBlog/label-name/iOS)の[Microsoft Defender for Endpointの新機能に関するページを](ios-whatsnew.md)参照してください。

- アプリ内フィードバック システムまたは[統合セキュリティ コンソール](https://security.microsoft.com)を介してフィードバックを提供する

## <a name="next-steps"></a>次の手順

- [登録済みデバイスのIntuneを介して iOS にMicrosoft Defender for Endpointを展開する](ios-install.md)
- [Defender for Endpoint リスクシグナル (MAM) を含めるアプリ保護ポリシーを構成する](ios-install-unmanaged.md)
- [iOS 機能用 Microsoft Defender for Endpoint を構成する](ios-configure-features.md)
- [Microsoft Defender for Endpointからのデバイス リスク スコアに基づいて条件付きアクセス ポリシーを構成する](ios-configure-features.md#conditional-access-with-defender-for-endpoint-on-ios)
- [モバイル アプリケーション管理 (MAM) の基本](/mem/intune/apps/app-management#mobile-application-management-mam-basics)
