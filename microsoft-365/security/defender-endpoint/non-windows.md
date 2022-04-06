---
title: Windows 以外のプラットフォームの Microsoft Defender for Endpoint
description: 非プラットフォームMicrosoft Defender for Endpoint機能の詳細Windowsする
keywords: Windows 以外、Mac、macos、Linux、android
search.product: eADQiWindows 10XVcnh
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
- M365-security-compliance
- m365solution-evalutatemtp
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 1dc7f7f29206b7944120bc2b494beec575313336
ms.sourcegitcommit: adea59259a5900cad5de29ddf46d1ca9e9e1c82f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/04/2022
ms.locfileid: "64632385"
---
# <a name="microsoft-defender-for-endpoint-for-non-windows-platforms"></a>Windows 以外のプラットフォームの Microsoft Defender for Endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint プラン 1 とプラン 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

Microsoft は、業界をリードするエンドポイント セキュリティ機能を Windows および Windows Server から macOS、Linux、Android、および iOS に拡張する取り組み中です。

組織は、さまざまなプラットフォームやデバイス間で脅威に直面しています。 Microsoft のチームは *、Microsoft だけでなく* *Microsoft からの* セキュリティ ソリューションの構築にも取り組み、お客様が異種環境を保護し、セキュリティを確保できます。 お客様からのフィードバックに耳を傾け、お客様のニーズに合ったソリューションを構築するために、お客様と密接に提携しています。

このMicrosoft Defender for Endpoint、お客様は、Microsoft 365 Defender ポータル内のすべての脅威とアラートを、Windowsと非サーバー間で統合Windows プラットフォームを使用して、環境内で何が起こっているかを完全に理解し、脅威の評価と対応を迅速に行えます。

## <a name="microsoft-defender-for-endpoint-on-macos"></a>macOS 用 Microsoft Defender for Endpoint

Microsoft Defender for Endpoint macOS では、最新リリースの 3 つのバージョンの macOS にエンドポイントでの検出と対応(EDR)、および脆弱性の管理機能が提供されます。 お客様は、ソリューションの展開と管理を、Microsoft エンドポイント マネージャー Jamf を通じて行います。 macOS 上Microsoft Officeアプリケーションと同様に、Microsoft Auto Update を使用して Mac 更新プログラムのMicrosoft Defender for Endpoint管理します。 主な機能と利点については、お知らせをご [覧ください](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/bg-p/MicrosoftDefenderATPBlog/label-name/macOS)。

開始方法の詳細については、「Defender for Endpoint on macOS」のドキュメントを参照 [してください](microsoft-defender-endpoint-mac.md)。

> [!NOTE]
> 次の機能は、現在 macOS エンドポイントではサポートされていません。
>
> - データ損失防止
> - セキュリティ管理のMicrosoft Defender for Endpoint

## <a name="microsoft-defender-for-endpoint-on-linux"></a>Linux 用 Microsoft Defender for Endpoint

Microsoft Defender for Endpointは、Linux サーバーの予防ウイルス対策 (AV)、エンドポイントでの検出と対応 (EDR)、脆弱性の管理機能を提供します。 これには、エージェントの構成と管理、スキャンの開始、脅威の管理を行う完全なコマンド ライン エクスペリエンスが含まれます。 RHEL 7.2+、CentOS Linux 7.2+、Ubuntu 16 LTS、SLES 12+、Debian 9+、Oracle Linux 7.2 の 6 つの最新バージョンがサポートされています。 Microsoft Defender for Endpointは、Puppet、Ansible、または既存の Linux 構成管理ツールを使用して展開および構成できます。 主な機能と利点については、お知らせをご [覧ください](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/bg-p/MicrosoftDefenderATPBlog/label-name/Linux)。

開始方法の詳細については、Linux のドキュメントの「Microsoft Defender for Endpoint」を参照[してください](microsoft-defender-endpoint-linux.md)。


> [!NOTE]
> Linux エンドポイントでは、現在、次の機能はサポートされていません。
>
> - データ損失防止
> - セキュリティ管理のMicrosoft Defender for Endpoint

## <a name="microsoft-defender-for-endpoint-on-android"></a>Android 用 Microsoft Defender for Endpoint

Microsoft Defender for Endpointは、Android 6.0 以上を実行しているデバイス向けモバイル脅威防御ソリューションです。 Android Enterprise (Work Profile) モードとデバイス管理者モードの両方がサポートされています。 Android では、フィッシング対策、安全でない接続のブロック、カスタムインジケーターの設定を含む Web 保護を提供しています。 このソリューションは、マルウェアや望ましくない可能性のあるアプリケーション (PUA) をスキャンし、Microsoft エンドポイント マネージャーおよび条件付きアクセスとの統合を通じて、追加の侵害防止機能を提供します。 主な機能と利点については、お知らせをご [覧ください](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/bg-p/MicrosoftDefenderATPBlog/label-name/Android)。

開始方法の詳細については、Android のドキュメントのMicrosoft Defender for Endpointを参照[してください](microsoft-defender-endpoint-android.md)。

## <a name="microsoft-defender-for-endpoint-on-ios"></a>iOS 用 Microsoft Defender for Endpoint API

Microsoft Defender for Endpointは、iOS 11.0 以上を実行しているデバイス向けモバイル脅威防御ソリューションです。 顧客のテナント内に登録されているデバイス (登録済みまたは登録されていない) がサポートされています。 監視対象デバイスと教師付き登録済みデバイスの両方がサポートされています。 iOS では、フィッシング対策、安全でない接続のブロック、カスタムインジケーターの設定、脱獄の検出など、Web 保護を提供しています。 主な機能と利点の詳細については、お知らせをご [覧ください](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/bg-p/MicrosoftDefenderATPBlog/label-name/iOS)。

開始方法の詳細については、iOS のドキュメントのMicrosoft Defender for Endpointを参照[してください](microsoft-defender-endpoint-ios.md)。

## <a name="licensing-requirements"></a>ライセンスの要件

対象となるライセンスユーザーは、最大 5 Microsoft Defender for Endpoint同時に使用できます。 Microsoft Defender for Endpoint (CSP) から購入クラウド ソリューション プロバイダー利用できます。

お客様は、Microsoft Defender for Endpoint/E5 または Microsoft 365 A5 セキュリティの一部として、スタンドアロン Microsoft Defender for Endpoint ライセンスを使用して macOS でMicrosoft 365取得できます。

Android および iOS Microsoft Defender for Endpointの最近発表された機能は、対象となるライセンスユーザー向け 5 つの認定デバイスの一部として、上記のオファーに含まれています。

Defender for Endpoint on Linux は、商用および教育の両方のお客様が利用できる Defender for Endpoint Server SKU を通じて利用できます。

料金と追加の適格性要件については、アカウント チームまたは CSP にお問い合わせください。
