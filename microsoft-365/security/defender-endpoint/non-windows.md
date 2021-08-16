---
title: Windows 以外のプラットフォームの Microsoft Defender for Endpoint
description: Microsoft Defender for Endpoint の非プラットフォーム向け機能Windowsする
keywords: Windows 以外、Mac、macos、Linux、android
search.product: eADQiWindows 10XVcnh
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
- M365-security-compliance
- m365solution-evalutatemtp
ms.topic: article
ms.technology: mde
ms.openlocfilehash: a975daa6b73f39722b077cda307aa5ea806b1e1b
ms.sourcegitcommit: a0185d6b0dd091db6e1e1bfae2f68ab0e3cf05e5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/13/2021
ms.locfileid: "58257002"
---
# <a name="microsoft-defender-for-endpoint-for-non-windows-platforms"></a>Windows 以外のプラットフォームの Microsoft Defender for Endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

Microsoft は、業界をリードするエンドポイント セキュリティ機能を、Windows および Windows Server から macOS、Linux、Android、および iOS に拡張する取り組み中です。

組織は、さまざまなプラットフォームやデバイス間で脅威に直面しています。 Microsoft のチームは *、Microsoft* だけでなく *Microsoft* からのセキュリティ ソリューションの構築にも取り組み、お客様が異種環境を保護し、セキュリティを確保できます。 お客様からのフィードバックに耳を傾け、お客様のニーズに合ったソリューションを構築するために、お客様と密接に提携しています。

Microsoft Defender for Endpoint を使用すると、Microsoft Defender セキュリティ センター プラットフォームと Windows Windows 以外のプラットフォームで、Microsoft Defender セキュリティ センター のすべての脅威とアラートの統合ビューを利用して、環境内で何が起こっているかを完全に理解し、脅威の評価と対応を迅速に行えます。

## <a name="microsoft-defender-for-endpoint-on-macos"></a>macOS 用 Microsoft Defender for Endpoint 

Microsoft Defender for Endpoint on macOS では、最新リリースバージョンの macOS に対して、ウイルス対策、エンドポイント検出と応答 (EDR)、脆弱性の管理 機能が提供されます。 顧客は、ソリューションを展開および管理するには、Microsoft エンドポイント マネージャー Jamf を使用します。 macOS 上Microsoft Officeアプリケーションと同様に、Microsoft Auto Update を使用して Microsoft Defender for Endpoint on Mac 更新プログラムを管理します。 主な機能と利点については、お知らせをご [覧ください](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/bg-p/MicrosoftDefenderATPBlog/label-name/macOS)。

開始方法の詳細については、「Defender for Endpoint on macOS」のドキュメントを参照 [してください](microsoft-defender-endpoint-mac.md)。

>[!NOTE]
>次の機能は、現在 macOS エンドポイントではサポートされていません。
>- データ損失防止
>- ライブ応答


## <a name="microsoft-defender-for-endpoint-on-linux"></a>Linux 用 Microsoft Defender for Endpoint

Microsoft Defender for Endpoint on Linux では、Linux サーバーの予防 (AV)、エンドポイント検出と応答 (EDR)、脆弱性の管理機能を提供します。 これには、エージェントの構成と管理、スキャンの開始、脅威の管理を行う完全なコマンド ライン エクスペリエンスが含まれます。 RHEL 7.2+、CentOS Linux 7.2+、Ubuntu 16 LTS、SLES 12+、Debian 9+、Oracle Linux 7.2 の 6 つの最新バージョンがサポートされています。 Microsoft Defender for Endpoint on Linux は、Puppet、Ansible、または既存の Linux 構成管理ツールを使用して展開および構成できます。 主な機能と利点については、お知らせをご [覧ください](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/bg-p/MicrosoftDefenderATPBlog/label-name/Linux)。

開始方法の詳細については、Microsoft Defender for Endpoint on Linux のドキュメントを参照 [してください](microsoft-defender-endpoint-linux.md)。

>[!NOTE]
>Linux エンドポイントでは、現在、次の機能はサポートされていません。
>- データ損失防止
>- ライブ応答
>- SIEM



## <a name="microsoft-defender-for-endpoint-on-android"></a>Android 用 Microsoft Defender for Endpoint

Microsoft Defender for Endpoint on Android は、Android 6.0 以上を実行しているデバイス向けモバイル脅威防御ソリューションです。 Android Enterprise (Work Profile) モードとデバイス管理者モードの両方がサポートされています。 Android では、フィッシング対策、安全でない接続のブロック、カスタムインジケーターの設定を含む Web 保護を提供しています。 このソリューションは、マルウェアや望ましくない可能性のあるアプリケーション (PUA) をスキャンし、Microsoft エンドポイント マネージャーおよび条件付きアクセスとの統合を通じて、追加の侵害防止機能を提供します。 主な機能と利点については、お知らせをご [覧ください](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/bg-p/MicrosoftDefenderATPBlog/label-name/Android)。

開始方法の詳細については、Android の Microsoft Defender for Endpoint のドキュメントを参照 [してください](microsoft-defender-endpoint-android.md)。

## <a name="microsoft-defender-for-endpoint-on-ios"></a>iOS 用 Microsoft Defender for Endpoint API

Microsoft Defender for Endpoint on iOS は、iOS 11.0 以上を実行しているデバイス向けモバイル脅威防御ソリューションです。 顧客のテナント内に登録されているデバイス (登録済みまたは登録されていない) がサポートされています。 監視対象デバイスと教師付き登録済みデバイスの両方がサポートされています。 iOS では、フィッシング対策、安全でない接続のブロック、カスタムインジケーターの設定、脱獄の検出など、Web 保護を提供しています。 主な機能と利点の詳細については、お知らせを [参照してください](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/bg-p/MicrosoftDefenderATPBlog/label-name/iOS)。 

開始方法の詳細については、iOS の Microsoft Defender for Endpoint のドキュメントを参照 [してください](microsoft-defender-endpoint-ios.md)。

## <a name="licensing-requirements"></a>ライセンスの要件 

対象となるライセンスユーザーは、最大 5 つの同時デバイスで Microsoft Defender for Endpoint を使用できます。 Microsoft Defender for Endpoint は、ユーザー (CSP) から購入クラウド ソリューション プロバイダー利用できます。

お客様は、スタンドアロンの Microsoft Defender for Endpoint ライセンス、Microsoft 365 A5/E5、または Microsoft 365 セキュリティの一部として、macOS 上の Microsoft Defender for Endpoint を取得できます。

Android および iOS 上の Microsoft Defender for Endpoint の最近発表された機能は、対象となるライセンスユーザー向け 5 つの認定デバイスの一部として、上記のオファーに含まれています。

Defender for Endpoint on Linux は、商用および教育の両方のお客様が利用できる Defender for Endpoint Server SKU を通じて利用できます。

料金と追加の適格性要件については、アカウント チームまたは CSP にお問い合わせください。
