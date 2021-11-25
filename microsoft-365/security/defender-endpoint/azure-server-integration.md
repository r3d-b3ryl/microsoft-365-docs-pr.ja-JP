---
title: Microsoft Defender for Cloudとの統合
description: Microsoft Defender for Endpoint と Microsoft Defender for Cloud との統合について説明します。
keywords: 統合、サーバー、azure、2012r2、2016、2019、サーバーオンボーディング、デバイス管理、エンドポイント サーバー用 Microsoft Defender の構成、Microsoft Defender for Endpoint サーバーのオンボード、Microsoft Defender for Endpoint サーバーのオンボード
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
author: mjcaparas
ms.author: macapara
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 4364855120524f7b6e993a3827a03a3bd5f79d96
ms.sourcegitcommit: 2b9d40e888ff2f2b3385e2a90b50d719bba1e653
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/25/2021
ms.locfileid: "61170546"
---
# <a name="integration-with-microsoft-defender-for-cloud"></a>Microsoft Defender for Cloudとの統合

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- Microsoft Defender for Cloud

Microsoft Defender for Endpoint は、Microsoft Defender for Cloud と統合して、包括的なサーバー保護ソリューションWindows提供できます。 この統合により、Microsoft Defender for Cloud は Defender for Endpoint の機能を使用して、セキュリティ サーバーの脅威検出を強化Windowsできます。

この統合には、次の機能が含まれています。

- 自動オンボーディング - Defender for Endpoint センサーは、Microsoft Defender for Cloud にオンボードWindowsサーバーで自動的に有効になります。 Microsoft Defender for Cloud オンボーディングの詳細については、「Use [the integrated Microsoft Defender for Endpoint license 」を参照してください](/azure/security-center/security-center-wdatp)。

    > [!NOTE]
    > Microsoft Defender for server と Microsoft Defender for Endpoint の統合は[、Windows Server 2019 と Windows Virtual Desktop (WVD)](/azure/security-center/release-notes#microsoft-defender-for-endpoint-integration-with-azure-defender-now-supports-windows-server-2019-and-windows-10-virtual-desktop-wvd-in-preview)をサポートするために拡張されました。

- Windowsによって監視される Microsoft Defender for Cloud サーバーは、Defender for Endpoint - Microsoft Defender for Cloud でエンドポイント用 Defender テナントにシームレスに接続し、クライアントとサーバー間で 1 つのビューを提供します。  さらに、Defender for Endpoint アラートは Microsoft Defender for Cloud コンソールで利用できます。
- サーバー調査 - Microsoft Defender for Cloud のお客様は、Microsoft Defender セキュリティ センターにアクセスして詳細な調査を実行し、潜在的な侵害の範囲を明らかにすることができます。

> [!IMPORTANT]
> - Microsoft Defender for Cloud を使用してサーバーを監視すると、Defender for Endpoint テナントが自動的に作成されます (米国のユーザーは米国、EU ではヨーロッパおよび英国のユーザー)。<br>
Defender for Endpoint によって収集されたデータは、プロビジョニング中に特定されたテナントの地理的位置に格納されます。
> - Microsoft Defender for Cloud を使用する前に Defender for Endpoint を使用する場合、後で Microsoft Defender for Cloud と統合した場合でも、テナントの作成時に指定した場所にデータが保存されます。
> - 構成が完了すると、データの保存場所を変更できません。 データを別の場所に移動する必要がある場合は、Microsoft サポートに問い合わせ、テナントをリセットする必要があります。 <br>
この統合を利用したサーバー エンドポイントの監視は、ユーザーのOffice 365 GCCされています。



## <a name="related-topics"></a>関連トピック
- [以前のバージョンの Windows をオンボードする](onboard-downlevel.md)
- [オンボード Windows Server 2012 R2、2016、SAC バージョン 1803、および 2019](configure-server-endpoints.md)
