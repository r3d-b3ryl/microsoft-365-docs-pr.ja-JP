---
title: Azure Defender との統合
description: Microsoft Defender for Endpoint と Azure Defender との統合について説明します。
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
ms.openlocfilehash: a702585a558cf6754cbd2eaf23d5061879120ac8
ms.sourcegitcommit: be095345257225394674698beb3feeb0696ec86d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/08/2021
ms.locfileid: "60240609"
---
# <a name="integration-with-azure-defender"></a>Azure Defender との統合

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- Microsoft Defender for Endpoint
- Azure Defender

Microsoft Defender for Endpoint は、Azure Defender と統合して、包括的なサーバー保護Windows提供できます。 この統合により、Azure Defender は Defender for Endpoint の機能を使用して、サーバーの脅威検出を強化Windowsできます。

この統合には、次の機能が含まれています。

- 自動オンボーディング - Defender for Endpoint センサーは、Azure Defender にオンボードWindowsサーバーで自動的に有効になります。 Azure Defender オンボーディングの詳細については、「統合 Microsoft Defender for Endpoint ライセンスを使用する [」を参照してください](/azure/security-center/security-center-wdatp)。

    > [!NOTE]
    > Azure Defender for Servers と Microsoft Defender for Endpoint の統合は[、Windows Server 2019 と Windows Virtual Desktop (WVD)](/azure/security-center/release-notes#microsoft-defender-for-endpoint-integration-with-azure-defender-now-supports-windows-server-2019-and-windows-10-virtual-desktop-wvd-in-preview)をサポートするように拡張されました。

- Windows監視されるサーバーは、Defender for Endpoint でも利用できます 。 Azure Defender は Defender for Endpoint テナントにシームレスに接続し、クライアントとサーバー間で 1 つのビューを提供します。  さらに、Defender for Endpoint アラートは Azure Defender コンソールで利用できます。
- サーバー調査 - Azure Defender のお客様は、Microsoft Defender セキュリティ センターにアクセスして詳細な調査を実行し、潜在的な侵害の範囲を明らかにできます。

> [!IMPORTANT]
> - Azure Defender を使用してサーバーを監視すると、Defender for Endpoint テナントが自動的に作成されます (米国のユーザーは米国、EU ではヨーロッパおよび英国のユーザー)。<br>
Defender for Endpoint によって収集されたデータは、プロビジョニング中に特定されたテナントの地理的位置に格納されます。
> - Azure Defender を使用する前に Defender for Endpoint を使用する場合、後で Azure Defender と統合した場合でも、テナントの作成時に指定した場所にデータが格納されます。
> - 構成が完了すると、データの保存場所を変更できません。 データを別の場所に移動する必要がある場合は、Microsoft サポートに問い合わせ、テナントをリセットする必要があります。 <br>
この統合を利用したサーバー エンドポイントの監視は、ユーザーのOffice 365 GCCされています。



## <a name="related-topics"></a>関連項目
- [以前のバージョンの Windows をオンボードする](onboard-downlevel.md)
- [オンボード Windows Server 2012 R2、2016、SAC バージョン 1803、および 2019](configure-server-endpoints.md)