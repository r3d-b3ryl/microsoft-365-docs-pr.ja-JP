---
title: iOS 用 Microsoft Defender for Endpoint API
ms.reviewer: ''
description: iOS に Microsoft Defender for Endpoint をインストールして使用する方法について説明します。
keywords: microsoft、 defender、 Microsoft Defender for Endpoint, ios, overview, installation, deploy, uninstallation, intune
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 4dc2d9e0d4ea06b7b51a29be11af4e6316c83bcc
ms.sourcegitcommit: ea4bc3b005d86b029700e56015a47b8cc6dca2a1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/25/2021
ms.locfileid: "58509571"
---
# <a name="microsoft-defender-for-endpoint-on-ios"></a>iOS 用 Microsoft Defender for Endpoint API

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

**Microsoft Defender for Endpoint on iOS** では、Web サイト、電子メール、アプリからのフィッシングや安全でないネットワーク接続に対する保護が提供されます。 すべてのアラートは、ウィンドウ内の 1 つのウィンドウからMicrosoft Defender セキュリティ センター。 このポータルにより、セキュリティ チームは、他のプラットフォームと共に、iOS デバイス上の脅威の一元的なビューを提供します。

> [!CAUTION]
> iOS で Defender for Endpoint と共に他のサード パーティ製のエンドポイント保護製品を実行すると、パフォーマンスの問題や予期しないシステム エラーが発生する可能性があります。

## <a name="pre-requisites"></a>前提条件

**エンド ユーザー向け**

- アプリのエンド ユーザーに割り当てられた Microsoft Defender for Endpoint ライセンス。 「Microsoft [Defender for Endpoint ライセンス要件」を参照してください](/microsoft-365/security/defender-endpoint/minimum-requirements#licensing-requirements)。

- **登録済みデバイスの場合**: デバイスは、Intune デバイスコンプライアンス ポリシーを適用Intune ポータル サイトアプリを介して登録されます。 [](/mem/intune/user-help/enroll-your-device-in-intune-ios) これには、エンド ユーザーにライセンスを割り当てるMicrosoft Intune必要があります。
    - Intune ポータル サイト Apple App Store から[ダウンロードできます](https://apps.apple.com/us/app/intune-company-portal/id719171358)。
    - Apple では、リダイレクトユーザーがアプリ ストアから他のアプリをダウンロードすることを許可していないので、この手順は、Microsoft Defender for Endpoint アプリにオンボーディングする前にユーザーが行う必要があります。

- **登録されていないデバイスの場合**: デバイスは、デバイスに登録Azure Active Directory。 これには、エンド ユーザーがアプリを介して[サインインMicrosoft Authenticator必要です](https://apps.apple.com/app/microsoft-authenticator/id983156458)。

- ライセンスを割り当てる方法の詳細については、「ユーザーにライセンスを割り当 [てる」を参照してください](/azure/active-directory/users-groups-roles/licensing-groups-assign)。

**管理者向け**

- ポータルへのアクセスMicrosoft Defender セキュリティ センターします。

- 管理センター [Microsoft エンドポイント マネージャーアクセスして](https://go.microsoft.com/fwlink/?linkid=2109431)、組織の登録済みユーザー グループにアプリを展開します。

    > [!NOTE]
    > - Microsoft Defender for Endpoint では、モバイル デバイス管理 (MDM) を使用していないが、Intune を使用してモバイル アプリケーションを管理しているユーザーに対して、管理アプリケーション内の組織のデータに対する保護を拡張しました。 また、このサポートは、他のエンタープライズ モビリティ管理ソリューションを使用しているお客様にも拡張しますが、モバイル アプリケーション管理 [(MAM)](/mem/intune/apps/mam-faq)には Intune を使用します。
    > - さらに、Microsoft Defender for Endpoint では、Intune モバイル デバイス管理 (MDM) を使用して登録されているデバイスが既にサポートされています。  

**システム要件**

- iOS 11.0 以上を実行している iOS デバイス。 iPadは、バージョン 1.1.15010101 以降で正式にサポートされています。

- デバイスは、アプリに登録するか、Intune ポータル サイト[を](https://apps.apple.com/us/app/intune-company-portal/id719171358)介して Azure Active Directoryに[Microsoft Authenticator。](https://apps.apple.com/app/microsoft-authenticator/id983156458)

## <a name="installation-instructions"></a>インストール手順

iOS での Microsoft Defender for Endpoint の展開は、MICROSOFT エンドポイント マネージャー (MEM) を介して行え、監視対象デバイスと教師付きデバイスの両方がサポートされています。 エンドユーザーは、Apple アプリ ストアからアプリを直接 [インストールすることもできます](https://aka.ms/mdatpiosappstore)。
詳細については [、「Deploy Microsoft Defender for Endpoint on iOS」を参照してください](ios-install.md)。

## <a name="resources"></a>リソース

- iOS またはブログの Microsoft Defender [for Endpoint](ios-whatsnew.md) の新機能にアクセスして、今後のリリースについて情報を得 [る](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/bg-p/MicrosoftDefenderATPBlog/label-name/iOS)。

- アプリ内フィードバック システムまたは SecOps ポータルを通じて [フィードバックを提供する](https://securitycenter.microsoft.com)

## <a name="next-steps"></a>次の手順

- [iOS での Microsoft Defender for Endpoint の展開](ios-install.md)
- [iOS の機能で Microsoft Defender for Endpoint を構成する](ios-configure-features.md)
- [Defender for Endpoint リスクシグナル (MAM) を含めるアプリ保護ポリシーを構成する](ios-install-unmanaged.md)
- [Microsoft Defender for Endpoint のデバイス リスク スコアに基づいて条件付きアクセス ポリシーを構成する](ios-configure-features.md#conditional-access-with-defender-for-endpoint-on-ios)
- [モバイル アプリケーション管理 (MAM) の基本](/mem/intune/apps/app-management#mobile-application-management-mam-basics)
