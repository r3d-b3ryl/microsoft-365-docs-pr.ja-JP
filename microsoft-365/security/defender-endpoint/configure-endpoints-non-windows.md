---
title: Windows以外のデバイスをMicrosoft Defender for Endpoint サービスにオンボードする
description: Microsoft Defender for Endpoint サービスにセンサー データを送信できるように、Windows以外のデバイスを構成します。
keywords: 非Windows デバイスのオンボード、macos、Linux、デバイス管理、Microsoft Defender for Endpointデバイスの構成
search.product: eADQiWindows 10XVcnh
search.appverid: met150
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
- m365-initiative-defender-endpoint
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 4573e7002454e9e72648df42352104abaa4c22d6
ms.sourcegitcommit: 6e90baef421ae06fd790b0453d3bdbf624b7f9c0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/12/2022
ms.locfileid: "62767654"
---
# <a name="onboard-non-windows-devices"></a>Windows 以外のデバイスをオンボードする

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

**プラットフォーム**
- macOS
- Linux

> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-nonwindows-abovefoldlink)

Defender for Endpoint は、Windows および非Windows プラットフォームに対して一元的なセキュリティ操作エクスペリエンスを提供します。 サポートされているさまざまなオペレーティング システム (OS) からのアラートをMicrosoft 365 Defenderに表示し、組織のネットワークを保護することができます。

統合を機能させるには、Defender for Endpoint と互換性のある Linux ディストリビューションと macOS の正確なバージョンを把握する必要があります。 詳細については、以下を参照してください。

- [Linux システム要件に関するMicrosoft Defender for Endpoint](microsoft-defender-endpoint-linux.md#system-requirements)
- [macOS のシステム要件に関するMicrosoft Defender for Endpoint](microsoft-defender-endpoint-mac.md#system-requirements)。

## <a name="onboarding-non-windows-devices"></a>Windows以外のデバイスのオンボード

Windows以外のデバイスをオンボードするには、次の手順を実行する必要があります。

1. オンボーディングの推奨方法を選択します。

   - macOS デバイスの場合は、Microsoft Defender for Endpointまたはサード パーティのソリューションを使用してオンボードすることを選択できます。 詳細については、「[Mac でのMicrosoft Defender for Endpoint」を](/microsoft-365/security/defender-endpoint/microsoft-defender-endpoint-mac)参照してください。

   - 他の非Windows デバイスの場合は、**サード パーティの統合を使用して非Windows デバイスをオンボード** するを選択します。
    1. ナビゲーション ウィンドウで、[ **パートナーと API** \> **パートナー アプリケーション** ] を選択します。 サード パーティのソリューションが一覧表示されていることを確認します。
    2. [**パートナー アプリケーション**] ページで、Windows以外のデバイスをサポートするパートナーを選択します。
    3. [ **表示]** をクリックしてパートナーのページを開きます。 ページに記載されている指示に従います。
    4. アカウントを作成した後、またはパートナー ソリューションをサブスクライブした後、組織内のテナントグローバル管理者がパートナー アプリケーションからのアクセス許可要求を受け入れるように求められる段階に到達する必要があります。 アクセス許可要求を注意深く読み取り、必要なサービスと一致していることを確認します。

2. サード パーティソリューションの指示に従って、検出テストを実行します。

## <a name="offboard-non-windows-devices"></a>オフボード非Windows デバイス

macOS および Linux デバイスの場合は、Microsoft Defender for Endpointを使用してオフボードを選択できます。 ナビゲーション ウィンドウで、[**オフボード**\>のオペレーティング システムの選択] **設定** \> **選択してオフボード プロセスを開始** します。

サード パーティの統合を無効にすることで、Windows以外のデバイスをオフボードすることもできます。 [サード パーティのソリューションを統合](https://security.microsoft.com/interoperability/partners)することで、Windows 以外のプラットフォームを実行しているデバイスのカバレッジを有効にします。

## <a name="related-topics"></a>関連項目
- [Windows デバイスのオンボード](configure-endpoints.md)
- [オンボード サーバー](configure-server-endpoints.md)
- [プロキシとインターネット接続の設定を構成する](configure-proxy-internet.md)
- [Microsoft Defender for Endpoint のオンボードの問題のトラブルシューティング](troubleshoot-onboarding.md)
