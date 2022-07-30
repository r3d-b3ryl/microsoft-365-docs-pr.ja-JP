---
title: Windows 以外のプラットフォームの Microsoft Defender for Endpoint
description: Windows 以外のプラットフォームのMicrosoft Defender for Endpoint機能について説明します
keywords: windows 以外, mac, macos, Linux, android
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
ms.openlocfilehash: 4e141b9764a1e677cb252d59c7ea6e5e555ccb84
ms.sourcegitcommit: e4882e3c66166ea7b834ad2e8fafeab42293e07d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/30/2022
ms.locfileid: "67099824"
---
# <a name="microsoft-defender-for-endpoint-for-non-windows-platforms"></a>Windows 以外のプラットフォームの Microsoft Defender for Endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint プラン 1 とプラン 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

Microsoft は、業界をリードするエンドポイント セキュリティ機能を Windows および Windows Server を超えて macOS、Linux、Android、iOS に拡張する取り組みを進めています。

組織は、さまざまなプラットフォームやデバイスにわたって脅威に直面しています。 Microsoft チームは *、Microsoft だけでなく**、Microsoft から* セキュリティ ソリューションを構築し、お客様が異種環境を保護してセキュリティで保護できるように取り組んでいます。 お客様のフィードバックに耳を傾け、お客様のニーズに合ったソリューションを構築するために、お客様と緊密に連携しています。

Microsoft Defender for Endpointを使用すると、お客様は、windows および Windows 以外のプラットフォーム全体で、Microsoft 365 Defender ポータル内のすべての脅威とアラートを一元的に表示し、環境内で何が起こっているかを完全に把握できるため、脅威をより迅速に評価して対応できるようになります。

## <a name="microsoft-defender-for-endpoint-on-macos"></a>macOS 用 Microsoft Defender for Endpoint

macOS のMicrosoft Defender for Endpointでは、最新リリースの 3 つのバージョンの macOS に対して、ウイルス対策、エンドポイント検出と応答 (EDR)、脆弱性管理機能が提供されます。 お客様は、Microsoft エンドポイント マネージャーと Jamf を通じてソリューションをデプロイおよび管理できます。 macOS 上の Microsoft Office アプリケーションと同様に、Microsoft Auto Update は Mac の更新プログラムでMicrosoft Defender for Endpointを管理するために使用されます。 主な機能と利点については、 [お知らせ](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/bg-p/MicrosoftDefenderATPBlog/label-name/macOS)を参照してください。

作業を開始する方法の詳細については、macOS の Defender for Endpoint [のドキュメントを参照してください](microsoft-defender-endpoint-mac.md)。

> [!NOTE]
> 現在、macOS エンドポイントでは次の機能はサポートされていません。
>
> - Microsoft Defender for Endpointのセキュリティ管理

## <a name="microsoft-defender-for-endpoint-on-linux"></a>Linux 用 Microsoft Defender for Endpoint

Linux 上のMicrosoft Defender for Endpointでは、予防的なウイルス対策 (AV)、エンドポイントの検出と応答 (EDR)、Linux サーバーの脆弱性管理機能が提供されます。 これには、エージェントの構成と管理、スキャンの開始、脅威の管理を行う完全なコマンド ライン エクスペリエンスが含まれます。 RHEL 7.2 以降、CentOS Linux 7.2 以降、Ubuntu 16 LTS、またはそれ以降の LTS、SLES 12 以降、Debian 9 以降、Oracle Linux 7.2 の 6 つの最も一般的な Linux Server ディストリビューションの最新バージョンがサポートされています。 Linux 上のMicrosoft Defender for Endpointは、Puppet、Ansible、または既存の Linux 構成管理ツールを使用してデプロイおよび構成できます。 主な機能と利点については、 [お知らせ](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/bg-p/MicrosoftDefenderATPBlog/label-name/Linux)を参照してください。

作業を開始する方法の詳細については、Linux のドキュメントのMicrosoft Defender for Endpointを[参照してください](microsoft-defender-endpoint-linux.md)。


> [!NOTE]
> Linux エンドポイントでは、現在、次の機能はサポートされていません。
>
> - データ損失防止
> - Microsoft Defender for Endpointのセキュリティ管理

## <a name="microsoft-defender-for-endpoint-on-android"></a>Android 用 Microsoft Defender for Endpoint

Android 上のMicrosoft Defender for Endpointは、Android 6.0 以降を実行しているデバイス向けのモバイル脅威防御ソリューションです。 Android Enterprise (仕事用プロファイル) モードとデバイス管理者モードの両方がサポートされています。 Android では、フィッシング対策、安全でない接続のブロック、カスタム インジケーターの設定など、Web 保護を提供しています。 このソリューションは、マルウェアや望ましくない可能性があるアプリケーション (PUA) をスキャンし、Microsoft エンドポイント マネージャーおよび条件付きアクセスとの統合を通じて、追加の侵害防止機能を提供します。 主な機能と利点については、 [お知らせ](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/bg-p/MicrosoftDefenderATPBlog/label-name/Android)を参照してください。

作業を開始する方法の詳細については、Android ドキュメントのMicrosoft Defender for Endpointを[参照してください](microsoft-defender-endpoint-android.md)。

## <a name="microsoft-defender-for-endpoint-on-ios"></a>iOS 用 Microsoft Defender for Endpoint API

iOS 上のMicrosoft Defender for Endpointは、iOS 11.0 以降を実行しているデバイス向けのモバイル脅威防御ソリューションです。 顧客のテナント内に登録されているデバイス (登録済みまたは登録解除済み) がサポートされます。 監視対象デバイスと教師なし登録済みデバイスの両方がサポートされています。 iOS では、フィッシング対策、安全でない接続のブロック、カスタム インジケーターの設定、脱獄検出などの Web 保護を提供しています。 主な機能と利点の詳細については、 [お知らせ](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/bg-p/MicrosoftDefenderATPBlog/label-name/iOS)を参照してください。

作業を開始する方法の詳細については、iOS ドキュメントのMicrosoft Defender for Endpointを[参照してください](microsoft-defender-endpoint-ios.md)。

## <a name="licensing-requirements"></a>ライセンスの要件

資格のあるライセンスユーザーは、最大 5 台の同時デバイスでMicrosoft Defender for Endpointを使用できます。 Microsoft Defender for Endpointは、クラウド ソリューション プロバイダー (CSP) から購入することもできます。

お客様は、Microsoft 365 A5/E5 または Microsoft 365 Security の一部として、スタンドアロンのMicrosoft Defender for Endpoint ライセンスを使用して macOS でMicrosoft Defender for Endpointを取得できます。

Android と iOS で最近発表されたMicrosoft Defender for Endpointの機能は、資格のあるライセンスユーザー向けの 5 つの認定デバイスの一部として、上記のオファーに含まれています。

Defender for Endpoint on Linux は、商用および教育機関の両方のお客様が利用できる Defender for Endpoint Server SKU から入手できます。

価格と追加の資格要件については、アカウント チームまたは CSP にお問い合わせください。
