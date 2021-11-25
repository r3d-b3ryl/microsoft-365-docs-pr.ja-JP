---
title: Microsoft Defender for Endpoint サービスWindowsデバイス以外のデバイスをオンボードする
description: Microsoft Defender for Endpoint サービスWindowsセンサー データを送信できるよう、デバイス以外のデバイスを構成します。
keywords: オンボードの非Windowsデバイス、macos、Linux、デバイス管理、エンドポイント デバイス用 Microsoft Defender の構成
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
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 4d4b83457fb8f8dc16891882cd8ca5c131659d35
ms.sourcegitcommit: eb8c600d3298dca1940259998de61621e6505e69
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/24/2021
ms.locfileid: "61167552"
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

Defender for Endpoint は、セキュリティ プラットフォームと非プラットフォームWindows一元的なセキュリティWindows提供します。 サポートされているさまざまなオペレーティング システム (OS) からのアラートを、組織のネットワークMicrosoft 365 Defender保護するために役立ちます。

統合を機能するには、Defender for Endpoint と互換性のある Linux ディストリビューションと macOS の正確なバージョンを知る必要があります。 詳細については、以下を参照してください。

- [Microsoft Defender for Endpoint on Linux システム要件](microsoft-defender-endpoint-linux.md#system-requirements)
- [Microsoft Defender for Endpoint on macOS system requirements](microsoft-defender-endpoint-mac.md#system-requirements).

## <a name="onboarding-non-windows-devices"></a>非デバイスのオンボードWindowsする

非デバイスをオンボードするには、次の手順を実行Windows必要があります。

1. オンボーディングの好みの方法を選択します。

   - macOS デバイスの場合は、Microsoft Defender for Endpoint またはサード パーティ製ソリューションを使用してオンボードを選択できます。 詳細については [、「Microsoft Defender for Endpoint on Mac」を参照してください](/microsoft-365/security/defender-endpoint/microsoft-defender-endpoint-mac)。

   - その他の非接続デバイスWindowsサードパーティとの統合を通じてWindowsデバイスのオンボード **を選択します**。
    1. ナビゲーション ウィンドウで、[パートナーと **API パートナー アプリケーション]** \> **を選択します** 。 サード パーティ製のソリューションが一覧に表示されます。
    2. [パートナー **アプリケーション] ページ** で、ユーザー以外のデバイスをサポートするパートナー Windowsします。
    3. [表示 **] を** クリックしてパートナーのページを開きます。 ページに記載されている手順に従います。
    4. アカウントを作成するか、パートナー ソリューションをサブスクライブした後、組織のテナントのグローバル管理者がパートナー アプリケーションからのアクセス許可要求を受け入れるという要求を受け入れるステージに進む必要があります。 アクセス許可要求を注意深く読んで、必要なサービスと一致している必要があります。

2. サード パーティソリューションの指示に従って検出テストを実行します。

## <a name="offboard-non-windows-devices"></a>オフボードの非Windowsデバイス

macOS および Linux デバイスの場合は、Microsoft Defender for Endpoint からオフボードを選択できます。 ナビゲーション ウィンドウで、[オフボードの選択 **設定** オペレーティング システムの選択] を選択 \>  \> **して、オフボード プロセスを開始します**。

サードパーティの統合を無効にすることで、Windows以外のデバイスをオフボードすることもできます。 サードパーティのソリューションを統合することで、Windowsプラットフォームを実行しているデバイスのカバレッジ[を有効にします](https://securitycenter.windows.com/interoperability/partners)。 

## <a name="related-topics"></a>関連トピック
- [Windows デバイスのオンボード](configure-endpoints.md)
- [オンボード サーバー](configure-server-endpoints.md)
- [プロキシとインターネット接続の設定を構成する](configure-proxy-internet.md)
- [Microsoft Defender for Endpoint オンボーディングの問題のトラブルシューティング](troubleshoot-onboarding.md)
