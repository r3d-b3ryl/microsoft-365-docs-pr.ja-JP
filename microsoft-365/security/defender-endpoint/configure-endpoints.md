---
title: Windows 10 デバイスのオンボード ツールと各種方法
description: センサー データを Microsoft Defender ATP センサーに送信できるよう、Windows 10 デバイスをオンボードする
keywords: オンボード Windows 10 デバイス、グループ ポリシー、エンドポイント構成マネージャー、モバイル デバイス管理、ローカル スクリプト、gp、sccm、mdm、intune
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
ms.openlocfilehash: 1831d8927e761827f9bbcee84551433b68e3c6cc
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2021
ms.locfileid: "51165539"
---
# <a name="onboarding-tools-and-methods-for-windows-10-devices"></a>Windows 10 デバイスのオンボード ツールと各種方法

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)
- [Microsoft 365 Endpoint データ損失防止 (DLP)](/microsoft-365/compliance/endpoint-dlp-learn-about)

>Defender for Endpoint を体験してみませんか? [無料試用版にサインアップします。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

Defender for Endpoint サービスがセンサー データを取得できるよう、組織内のデバイスを構成する必要があります。 組織内のデバイスを構成するために使用できるさまざまな方法と展開ツールがあります。

次の展開ツールとメソッドがサポートされています。

- グループ ポリシー
- Microsoft Endpoint Configuration Manager
- モバイル デバイスの管理 (Microsoft Intune を含む)
- ローカル スクリプト

## <a name="in-this-section"></a>このセクションの内容
トピック | 説明
:---|:---
[グループ ポリシーを使用した Windows 10 デバイスのオンボード](configure-endpoints-gp.md) | グループ ポリシーを使用して、構成パッケージをデバイスに展開します。
[Microsoft Endpoint Configuration Manager を使用した Windows デバイスのオンボード](configure-endpoints-sccm.md) | デバイスに構成パッケージを展開するには、Microsoft Endpoint Manager (現在のブランチ) バージョン 1606 または Microsoft Endpoint Manager (現在のブランチ) バージョン 1602 以前を使用できます。
[モバイル デバイス管理ツールを使用した Windows 10 デバイスのオンボード](configure-endpoints-mdm.md) | デバイスに構成パッケージを展開するには、モバイル デバイス管理ツールまたは Microsoft Intune を使用します。
[ローカル スクリプトを使用した Windows 10 デバイスのオンボード](configure-endpoints-script.md) | ローカル スクリプトを使用してエンドポイントに構成パッケージを展開する方法について説明します。
[非永続的な仮想デスクトップ インフラストラクチャ (VDI) デバイスのオンボード](configure-endpoints-vdi.md) | 構成パッケージを使用して VDI デバイスを構成する方法について説明します。


>Defender for Endpoint を体験してみませんか? [無料試用版にサインアップします。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configureendpoints-belowfoldlink)
