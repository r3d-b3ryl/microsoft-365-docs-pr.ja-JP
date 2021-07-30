---
title: Windows 10 デバイスのオンボード ツールと各種方法
description: オンボード Windows 10デバイスを使用して、センサー データを Microsoft Defender for Endpoint センサーに送信できます。
keywords: オンボード Windows 10、グループ ポリシー、エンドポイント構成マネージャー、モバイル デバイス管理、ローカル スクリプト、gp、sccm、mdm、intune
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
ms.openlocfilehash: 95ad09a3aca9b756752ef7fd05886e4d8c98befc
ms.sourcegitcommit: d817a3aecb700f7227a05cd165ffa7dbad67b09d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/29/2021
ms.locfileid: "53655829"
---
# <a name="onboarding-tools-and-methods-for-windows-10-devices-in-defender-for-endpoint"></a>Defender for Endpoint のデバイスWindows 10オンボーディング ツールとメソッド

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)
- [Microsoft 365エンドポイント データ損失防止 (DLP)](/microsoft-365/compliance/endpoint-dlp-learn-about)
- [Microsoft 365Insider リスク管理](/microsoft-365/compliance/insider-risk-management)

> Defender for Endpoint を体験してみませんか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-assignaccess-abovefoldlink)

Defender for Endpoint サービスがセンサー データを取得できるよう、組織内のデバイスを構成する必要があります。 組織内のデバイスを構成するために使用できるさまざまな方法と展開ツールがあります。

次の展開ツールとメソッドがサポートされています。

- グループ ポリシー
- Microsoft Endpoint Configuration Manager
- モバイル デバイスの管理 (Microsoft Intune を含む)
- ローカル スクリプト

## <a name="in-this-section"></a>このセクションの内容

トピック|説明
:---|:---
[グループ ポリシー Windows 10デバイスのオンボード](configure-endpoints-gp.md)|グループ ポリシーを使用して、構成パッケージをデバイスに展開します。
[デバイスWindowsデバイスのオンボードMicrosoft Endpoint Configuration Manager](configure-endpoints-sccm.md)|Microsoft エンドポイント マネージャー (現在のブランチ) バージョン 1606 または Microsoft エンドポイント マネージャー (現在のブランチ) バージョン 1602 以前を使用して、デバイスに構成パッケージを展開できます。
[モバイル デバイス管理ツールを使用した Windows 10 デバイスのオンボード](configure-endpoints-mdm.md)|デバイスに構成パッケージを展開するには、Microsoft Intune管理ツールまたはモバイル デバイス管理ツールを使用します。
[ローカル スクリプトを使用した Windows 10 デバイスのオンボード](configure-endpoints-script.md)|ローカル スクリプトを使用してエンドポイントに構成パッケージを展開する方法について説明します。
[非永続的な仮想デスクトップ インフラストラクチャ (VDI) デバイスのオンボード](configure-endpoints-vdi.md)|構成パッケージを使用して VDI デバイスを構成する方法について説明します。

> Defender for Endpoint を体験してみませんか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-configureendpoints-belowfoldlink)
