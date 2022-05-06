---
title: Microsoft Defender for Cloudとの統合
description: Microsoft Defender for CloudとのMicrosoft Defender for Endpoint統合について学習する
keywords: integration, server, azure, 2012r2, 2016, 2019, サーバーオンボーディング, デバイス管理, Microsoft Defender for Endpoint サーバーの構成, Microsoft Defender for Endpoint サーバーのオンボード, Microsoft Defender for Endpointのオンボードサーバー
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
author: mjcaparas
ms.author: macapara
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 2ed9d25336cd7e8162849aa5d1d1a3e3382063fc
ms.sourcegitcommit: 3fb76db6b34e24569417f4c8a41b99f46a780389
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/17/2022
ms.locfileid: "63526678"
---
# <a name="integration-with-microsoft-defender-for-cloud"></a>Microsoft Defender for Cloudとの統合

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- Microsoft Defender for Cloud

Microsoft Defender for Endpointは、Microsoft Defender for Cloudと統合して、包括的なWindowsサーバー保護ソリューションを提供できます。 この統合により、Microsoft Defender for Cloudは Defender for Endpoint の機能を使用して、Windows サーバーの脅威検出を強化できます。

この統合には、次の機能が含まれています。

- 自動オンボード - Defender for Endpoint センサーは、Microsoft Defender for CloudにオンボードされているWindows サーバーで自動的に有効になります。 オンボードのMicrosoft Defender for Cloudの詳細については、「[統合Microsoft Defender for Endpoint ライセンスを使用する](/azure/security-center/security-center-wdatp)」を参照してください。

    > [!NOTE]
    > Microsoft Defender for servers とMicrosoft Defender for Endpointの統合は、[Windows Server 2019 と Windows Virtual Desktop (WVD)](/azure/security-center/release-notes#microsoft-defender-for-endpoint-integration-with-azure-defender-now-supports-windows-server-2019-and-windows-10-virtual-desktop-wvd-in-preview) をサポートするように拡張されました。

- Microsoft Defender for Cloudによって監視されるWindows サーバーは、Defender for Endpoint でも使用できます。Microsoft Defender for Cloud Defender for Endpoint テナントにシームレスに接続し、クライアントとサーバー間で 1 つのビューを提供します。  さらに、Defender for Endpoint アラートは、Microsoft Defender for Cloud コンソールで利用できます。
- サーバー調査 - Microsoft Defender for Cloudお客様は、Microsoft 365 Defender ポータルにアクセスして詳細な調査を実行し、潜在的な侵害の範囲を明らかにすることができます。

> [!IMPORTANT]
> - Microsoft Defender for Cloudを使用してサーバーを監視すると、Defender for Endpoint テナントが自動的に作成されます (米国ユーザーの場合は米国、EU ではヨーロッパおよび英国のユーザー)。<br>
Defender for Endpoint によって収集されたデータは、プロビジョニング中に識別されたテナントの地理的な場所に格納されます。
> - Microsoft Defender for Cloud を使用する前に Defender for Endpoint を使用する場合、後で Microsoft Defender for Cloud と統合した場合でも、テナントの作成時に指定した場所にデータが格納されます。
> - 構成が完了すると、データの格納場所を変更することはできません。 データを別の場所に移動する必要がある場合は、Microsoft サポートに連絡してテナントをリセットする必要があります。 <br>
この統合を利用するサーバー エンドポイントの監視は、Office 365 GCC の顧客に対して無効になっています。



## <a name="related-topics"></a>関連項目
- [以前のバージョンの Windows をオンボードする](onboard-downlevel.md)
- [Windows Server 2012 R2、2016、SAC バージョン 1803、および 2019 をオンボードする](configure-server-endpoints.md)
