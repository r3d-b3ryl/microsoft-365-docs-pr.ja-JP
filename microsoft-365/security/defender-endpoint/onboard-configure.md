---
title: デバイスを Microsoft Defender for Endpoint サービスにオンボードする
description: Windows 10 デバイス、サーバー、Windows 以外のデバイスをオンボードし、検出テストを実行する方法について学習します。
keywords: オンボーディング、Microsoft Defender for Endpoint オンボーディング、sccm、グループ ポリシー、mdm、ローカル スクリプト、検出テスト
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
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 05cc5770df5bb05687bb8be69ad89a7abd6875ed
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933555"
---
# <a name="onboard-devices-to-the-microsoft-defender-for-endpoint-service"></a>デバイスを Microsoft Defender for Endpoint サービスにオンボードする

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

[!include[Prerelease information](../../includes/prerelease.md)]

>Defender for Endpoint を体験してみませんか? [無料試用版にサインアップしてください。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-onboardconfigure-abovefoldlink)

Defender for Endpoint ポータルのオンボーディング セクションに移動して、サポートされているデバイスをオンボードする必要があります。 デバイスに応じて、適切な手順と、デバイスに適した管理および展開ツールのオプションが提供されます。 

一般に、デバイスをサービスにオンボードするには、次の情報を使用します。

- デバイスが最小要件を満 [たしていることを確認する](minimum-requirements.md)
- デバイスに応じて、Defender for Endpoint ポータルのオンボーディング セクションに示されている構成手順に従います。
- デバイスに適切な管理ツールと展開方法を使用する
- 検出テストを実行して、デバイスが適切にオンボードされ、サービスに報告されていることを確認する

>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4bGqr]

## <a name="onboarding-tool-options"></a>オンボーディング ツールのオプション
次の表に、オンボードする必要があるエンドポイントに基づいて使用可能なツールを示します。

| Endpoint     | ツール オプション                       |
|--------------|------------------------------------------|
| **Windows**  |  [ローカル スクリプト (最大 10 台のデバイス)](configure-endpoints-script.md) <br>  [グループ ポリシー](configure-endpoints-gp.md) <br>  [Microsoft Endpoint Manager/ Mobile Device Manager](configure-endpoints-mdm.md) <br>   [Microsoft Endpoint Configuration Manager](configure-endpoints-sccm.md) <br> [VDI スクリプト](configure-endpoints-vdi.md)   |
| **macOS**    | [ローカル スクリプト](mac-install-manually.md) <br> [Microsoft エンドポイント マネージャー](mac-install-with-intune.md) <br> [JAMF Pro](mac-install-with-jamf.md) <br> [モバイル デバイス管理](mac-install-with-other-mdm.md) |
| **Linux Server** | [ローカル スクリプト](linux-install-manually.md) <br> [Puppet](linux-install-with-puppet.md) <br> [Ansible](linux-install-with-ansible.md)|
| **iOS**      | [アプリベース](ios-install.md)                                |
| **Android**  | [Microsoft エンドポイント マネージャー](android-intune.md)               | 




## <a name="in-this-section"></a>このセクションの内容
トピック | 説明
:---|:---
[以前のバージョンの Windows をオンボードする](onboard-downlevel.md)| Windows 7 および Windows 8.1 デバイスを Defender for Endpoint にオンボードします。 
[Windows 10 デバイスのオンボード](configure-endpoints.md) | Defender for Endpoint サービスに報告するには、デバイスをオンボードする必要があります。 エンタープライズでデバイスを構成するために使用できるツールと方法について説明します。
[オンボード サーバー](configure-server-endpoints.md) |  オンボード Windows Server 2008 R2 SP1、Windows Server 2012 R2、Windows Server 2016、Windows Server (SAC) バージョン 1803 以降、Windows Server 2019 以降、および Windows Server 2019 Core Edition to Defender for Endpoint。
[Windows 以外のデバイスをオンボードする](configure-endpoints-non-windows.md) | Defender for Endpoint は、Windows および Windows 以外のプラットフォームに対して一元的なセキュリティ操作エクスペリエンスを提供します。 Microsoft Defender Security Center でサポートされているさまざまなオペレーティング システム (OS) からのアラートを確認し、組織のネットワークをより保護することができます。 このエクスペリエンスは、サードパーティのセキュリティ製品のセンサー データを活用します。 
[新しくオンボードされたデバイスで検出テストを実行する](run-detection-test.md) | 新しくオンボードされたデバイスでスクリプトを実行して、Defender for Endpoint サービスに適切に報告されていることを確認します。
[プロキシとインターネットの設定を構成する](configure-proxy-internet.md)| プロキシとインターネット接続の設定を構成して、Defender for Endpoint クラウド サービスとの通信を有効にします。
[オンボーディングに関する問題のトラブルシューティング](troubleshoot-onboarding.md) | オンボーディング中に発生する可能性のある問題の解決について説明します。

>Defender for Endpoint を体験してみませんか? [無料試用版にサインアップしてください。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-onboardconfigure-belowfoldlink)
