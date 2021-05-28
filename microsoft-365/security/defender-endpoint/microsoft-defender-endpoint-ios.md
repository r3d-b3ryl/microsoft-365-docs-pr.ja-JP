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
ms.openlocfilehash: 4a051742775c3d4e8b36bf0ba7a4fd2502763014
ms.sourcegitcommit: 5377b00703b6f559092afe44fb61462e97968a60
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/27/2021
ms.locfileid: "52694463"
---
# <a name="microsoft-defender-for-endpoint-on-ios"></a>iOS 用 Microsoft Defender for Endpoint API

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

**Microsoft Defender for Endpoint on iOS** では、Web サイト、電子メール、アプリからのフィッシングや安全でないネットワーク接続に対する保護が提供されます。 すべてのアラートは、Microsoft Defender セキュリティ センターの 1 つのウィンドウから利用できます。 このポータルにより、セキュリティ チームは、他のプラットフォームと共に、iOS デバイス上の脅威の一元的なビューを提供します。

> [!CAUTION]
> iOS で Defender for Endpoint と共に他のサード パーティ製のエンドポイント保護製品を実行すると、パフォーマンスの問題や予期しないシステム エラーが発生する可能性があります。

## <a name="pre-requisites"></a>前提条件

**エンド ユーザー向け**

- アプリのエンド ユーザーに割り当てられた Microsoft Defender for Endpoint ライセンス。 「Microsoft [Defender for Endpoint ライセンス要件」を参照してください](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/minimum-requirements#licensing-requirements)。

- デバイスは Intune [ポータル](https://docs.microsoft.com/mem/intune/user-help/enroll-your-device-in-intune-ios) サイト アプリを介して登録され、Intune デバイス コンプライアンス ポリシーを適用します。 これには、エンド ユーザーに Microsoft Intune ライセンスが割り当てられている必要があります。
    - Intune ポータル サイト アプリは [、Apple App Store からダウンロードできます](https://apps.apple.com/us/app/intune-company-portal/id719171358)。
    - Apple では、リダイレクトユーザーがアプリ ストアから他のアプリをダウンロードすることを許可していないので、この手順は、Microsoft Defender for Endpoint アプリにオンボーディングする前にユーザーが行う必要があります。

- ライセンスを割り当てる方法の詳細については、「ユーザーにライセンスを割り当 [てる」を参照してください](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign)。

**管理者向け**

- Microsoft Defender セキュリティ センター ポータルへのアクセス。

    > [!NOTE]
    > Microsoft Intune は、iOS に Microsoft Defender for Endpoint を展開する場合にサポートされている唯一のモバイル デバイス管理 (MDM) ソリューションです。 現在、Intune で iOS 関連のデバイス コンプライアンス ポリシーで Defender for Endpoint を適用する場合は、現在登録されているデバイスだけがサポートされています。

- 組織の [登録済みユーザー](https://go.microsoft.com/fwlink/?linkid=2109431)グループにアプリを展開するには、Microsoft Endpoint Manager 管理センターにアクセスします。

**システム要件**

- iOS 11.0 以上を実行している iOS デバイス。 iPad デバイスは、バージョン 1.1.15010101 以降で正式にサポートされています。

- デバイスは Intune ポータル サイト アプリ [に登録されています](https://apps.apple.com/us/app/intune-company-portal/id719171358)。

> [!NOTE]
> **iOS 上のエンドポイント用 Microsoft Defender は [、Apple App Store で利用できます](https://aka.ms/mdatpiosappstore)。**

## <a name="installation-instructions"></a>インストール手順

iOS での Microsoft Defender for Endpoint の展開は Microsoft Intune (MDM) 経由であり、監視対象デバイスと教師付きデバイスの両方がサポートされています。
詳細については [、「Deploy Microsoft Defender for Endpoint on iOS」を参照してください](ios-install.md)。

## <a name="resources"></a>リソース

- iOS またはブログの Microsoft Defender [for Endpoint](ios-whatsnew.md) の新機能にアクセスして、今後のリリースについて情報を得 [る](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/bg-p/MicrosoftDefenderATPBlog/label-name/iOS)。

- アプリ内フィードバック システムまたは SecOps ポータルを通じて [フィードバックを提供する](https://securitycenter.microsoft.com)

## <a name="next-steps"></a>次の手順

- [iOS での Microsoft Defender for Endpoint の展開](ios-install.md)
- [iOS の機能で Microsoft Defender for Endpoint を構成する](ios-configure-features.md)
