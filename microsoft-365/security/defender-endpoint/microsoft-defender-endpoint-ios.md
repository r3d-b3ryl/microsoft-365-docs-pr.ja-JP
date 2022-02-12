---
title: iOS 用 Microsoft Defender for Endpoint API
ms.reviewer: ''
description: iOS に Microsoft Defender for Endpoint をインストールして使用する方法について説明します。
keywords: microsoft、 defender、 Microsoft Defender for Endpoint, ios, overview, installation, deploy, uninstallation, intune
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
ms.openlocfilehash: 3e0246160424e76d0ddce42b3dacf74c6b56e43c
ms.sourcegitcommit: 6e90baef421ae06fd790b0453d3bdbf624b7f9c0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/12/2022
ms.locfileid: "62765077"
---
# <a name="microsoft-defender-for-endpoint-on-ios"></a>iOS 用 Microsoft Defender for Endpoint API

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

**Microsoft Defender for Endpoint on iOS** では、Web サイト、電子メール、アプリからのフィッシングや安全でないネットワーク接続に対する保護が提供されます。 すべてのアラートは、ポータルの単一のウィンドウからMicrosoft 365 Defenderされます。 このポータルにより、セキュリティ チームは、他のプラットフォームと共に、iOS デバイス上の脅威の一元的なビューを提供します。

> [!CAUTION]
> iOS で Defender for Endpoint と共に他のサード パーティ製のエンドポイント保護製品を実行すると、パフォーマンスの問題や予期しないシステム エラーが発生する可能性があります。

## <a name="pre-requisites"></a>前提条件

**エンド ユーザー向け**

- アプリのエンド ユーザーに割り当てられた Microsoft Defender for Endpoint ライセンス。 [「Microsoft Defender for Endpoint ライセンス要件」を参照してください](/microsoft-365/security/defender-endpoint/minimum-requirements#licensing-requirements)。

- **登録済みデバイスの場合**:
    - デバイスは、Intune [デバイス](/mem/intune/user-help/enroll-your-device-in-intune-ios) コンプライアンス ポリシーを適用Intune ポータル サイトアプリを介して登録されます。 これには、エンド ユーザーにライセンスを割り当てるMicrosoft Intune必要があります。
    - Intune ポータル サイト Apple [App Store からダウンロードできます](https://apps.apple.com/us/app/intune-company-portal/id719171358)。
    
    >[!NOTE]
    >Apple では、リダイレクトユーザーがアプリ ストアから他のアプリをダウンロードすることを許可していないので、この手順をユーザーが Microsoft Defender for Endpoint アプリにオンボーディングする前に実行する必要があります)。
    
    - デバイスは、デバイスに登録Azure Active Directory。 これには、エンド ユーザーがアプリを介して[サインインMicrosoft Authenticatorがあります](https://apps.apple.com/app/microsoft-authenticator/id983156458)。

- **登録されていないデバイスの場合**:デバイスはデバイスに登録Azure Active Directory。 これには、エンド ユーザーがアプリを介して[サインインMicrosoft Authenticatorがあります](https://apps.apple.com/app/microsoft-authenticator/id983156458)。

- ライセンスを割り当てる方法の詳細については、「ユーザーにライセンスを割り当 [てる」を参照してください](/azure/active-directory/users-groups-roles/licensing-groups-assign)。

**管理者向け**

- ポータルへのアクセスMicrosoft 365 Defenderします。

- 管理センター [Microsoft エンドポイント マネージャーアクセス:](https://go.microsoft.com/fwlink/?linkid=2109431)
   - 組織の登録済みユーザー グループにアプリを展開します。
   - アプリ保護ポリシー (MAM) で Microsoft Defender for Endpoint リスクシグナルを構成する


    > [!NOTE]
    > - Microsoft Defender for Endpoint では、モバイル デバイス管理 (MDM) を使用していないが、Intune を使用してモバイル アプリケーションを管理しているユーザーに対して、管理アプリケーション内の組織のデータに対する保護を拡張しました。 また、このサポートは、他のエンタープライズ モビリティ管理ソリューションを使用しているお客様にも拡張しますが、モバイル アプリケーション管理 [(MAM)](/mem/intune/apps/mam-faq) には Intune を使用します。
    > - さらに、Microsoft Defender for Endpoint では、Intune モバイル デバイス管理 (MDM) を使用して登録されているデバイスが既にサポートされています。  

**システム要件**

- iOS 12.0 以上を実行している iOS デバイス。 iPad もサポートされています。

- デバイスは、Intune ポータル サイトアプリに登録するか[](https://apps.apple.com/us/app/intune-company-portal/id719171358)、同じアカウント[Azure Active Directory Microsoft Authenticatorに](https://apps.apple.com/app/microsoft-authenticator/id983156458)登録されます。

## <a name="installation-instructions"></a>インストール手順

iOS での Microsoft Defender for Endpoint の展開は、MICROSOFT エンドポイント マネージャー (MEM) を介して行え、監視対象デバイスと教師付きデバイスの両方がサポートされています。 エンドユーザーは、Apple アプリ ストアからアプリを直接 [インストールすることもできます](https://aka.ms/mdatpiosappstore)。

- Microsoft Defender for Endpoint on iOS を使用して登録されたデバイスMicrosoft エンドポイント マネージャー展開する方法については、「[Deploy Microsoft Defender for Endpoint on iOS」を参照してください](ios-install.md)。
- アプリ保護ポリシー (MAM) で Defender for Endpoint を使用する方法の詳細については、「Defender [for Endpoint risk signals (MAM)](ios-install-unmanaged.md) を含めるアプリ保護ポリシーの構成」を参照してください。

## <a name="resources"></a>リソース

- iOS またはブログの [Microsoft Defender for Endpoint](ios-whatsnew.md) の新機能にアクセスして、今後のリリースに関する情報を確認 [してください](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/bg-p/MicrosoftDefenderATPBlog/label-name/iOS)。

- アプリ内フィードバック システムまたは統合セキュリティ コンソールを通じて [フィードバックを提供する](https://security.microsoft.com)

## <a name="next-steps"></a>次の手順

- [登録済みデバイス用に Intune を介して iOS 上の Microsoft Defender for Endpoint を展開する](ios-install.md)
- [Defender for Endpoint リスクシグナル (MAM) を含めるアプリ保護ポリシーを構成する](ios-install-unmanaged.md)
- [iOS の機能で Microsoft Defender for Endpoint を構成する](ios-configure-features.md)
- [Microsoft Defender for Endpoint のデバイス リスク スコアに基づいて条件付きアクセス ポリシーを構成する](ios-configure-features.md#conditional-access-with-defender-for-endpoint-on-ios)
- [モバイル アプリケーション管理 (MAM) の基本](/mem/intune/apps/app-management#mobile-application-management-mam-basics)
