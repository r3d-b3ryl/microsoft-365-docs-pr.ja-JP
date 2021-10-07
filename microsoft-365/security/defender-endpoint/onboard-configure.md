---
title: デバイスを Microsoft Defender for Endpoint サービスにオンボードする
description: オンボード Windows、サーバー、非デバイスWindows、検出テストを実行する方法について学習します。
keywords: オンボーディング、Microsoft Defender for Endpoint オンボーディング、sccm、グループ ポリシー、mdm、ローカル スクリプト、検出テスト
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 52083cbd8b7e94c09c21ef434634376966102df6
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2021
ms.locfileid: "60178325"
---
# <a name="onboard-devices-to-the-microsoft-defender-for-endpoint-service"></a>デバイスを Microsoft Defender for Endpoint サービスにオンボードする

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

[!include[Prerelease information](../../includes/prerelease.md)]

> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-onboardconfigure-abovefoldlink)

Defender for Endpoint ポータルのオンボーディング セクションに移動して、サポートされているデバイスをオンボードする必要があります。 デバイスに応じて、適切な手順と、デバイスに適した管理および展開ツールのオプションが提供されます。

一般に、デバイスをサービスにオンボードするには、次の情報を使用します。

- デバイスが最小要件を満 [たしていることを確認する](minimum-requirements.md)
- デバイスに応じて、Defender for Endpoint ポータルのオンボーディング セクションに示されている構成手順に従います。
- デバイスに適切な管理ツールと展開方法を使用する
- 検出テストを実行して、デバイスが適切にオンボードされ、サービスに報告されていることを確認する

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4bGqr]

## <a name="onboarding-tool-options"></a>オンボーディング ツールのオプション

次の表に、オンボードする必要があるエンドポイントに基づいて使用可能なツールを示します。

|エンドポイント|ツール オプション|
|---|---|
|**Windows**|[ローカル スクリプト (最大 10 台のデバイス)](configure-endpoints-script.md) <p> [グループ ポリシー](configure-endpoints-gp.md) <p> [Microsoft エンドポイント マネージャー/ モバイル デバイス マネージャー](configure-endpoints-mdm.md) <p> [Microsoft Endpoint Configuration Manager](configure-endpoints-sccm.md) <p> [VDI スクリプト](configure-endpoints-vdi.md) <p> [Azure Defender との統合](configure-server-endpoints.md#integration-with-azure-defender)|
|**macOS**|[ローカル スクリプト](mac-install-manually.md) <p> [Microsoft エンドポイント マネージャー](mac-install-with-intune.md) <p> [JAMF Pro](mac-install-with-jamf.md) <p> [モバイル デバイス管理](mac-install-with-other-mdm.md)|
|**Linux Server**|[ローカル スクリプト](linux-install-manually.md) <p> [Puppet](linux-install-with-puppet.md) <p> [Ansible](linux-install-with-ansible.md)|
|**iOS**|[アプリベース](ios-install.md)|
|**Android**|[Microsoft エンドポイント マネージャー](android-intune.md)|

## <a name="in-this-section"></a>このセクションの内容

トピック|説明
:---|:---
[以前のバージョンの Windows をオンボードする](onboard-downlevel.md)|Defender for Endpoint Windows 7 および Windows 8.1デバイスをオンボードします。
[Windows デバイスのオンボード](configure-endpoints.md)|Defender for Endpoint サービスに報告するには、デバイスをオンボードする必要があります。 エンタープライズでデバイスを構成するために使用できるツールと方法について説明します。
[オンボード サーバー](configure-server-endpoints.md)|Windows Server 2008 R2 SP1、Windows Server 2012 R2、Windows Server 2016、Windows Server (SAC) バージョン 1803 以降、Windows Server 2019 以降、Windows Server 2019 コア エディションを Defender for Endpoint に搭載します。
[Windows 以外のデバイスをオンボードする](configure-endpoints-non-windows.md)|Defender for Endpoint は、セキュリティ プラットフォームだけでなく、Windowsプラットフォームにも一元的なセキュリティWindows提供します。 サポートされているさまざまなオペレーティング システム (OS) からのアラートを、組織のネットワークMicrosoft Defender セキュリティ センター保護することができます。 このエクスペリエンスは、サードパーティのセキュリティ製品のセンサー データを活用します。
[新しくオンボードされたデバイスで検出テストを実行する](run-detection-test.md)|新しくオンボードされたデバイスでスクリプトを実行して、Defender for Endpoint サービスに適切に報告されていることを確認します。
[プロキシとインターネットの設定を構成する](configure-proxy-internet.md)|プロキシとインターネット接続の設定を構成して、Defender for Endpoint クラウド サービスとの通信を有効にします。
[オンボーディングに関する問題のトラブルシューティング](troubleshoot-onboarding.md)|オンボーディング中に発生する可能性のある問題の解決について説明します。

> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-onboardconfigure-belowfoldlink)
