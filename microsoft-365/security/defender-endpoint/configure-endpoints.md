---
title: デバイスのオンボーディング ツールWindows方法
description: オンボード Windowsデバイスを使用して、センサー データを Microsoft Defender for Endpoint センサーに送信できます。
keywords: オンボード Windows、グループ ポリシー、エンドポイント構成マネージャー、モバイル デバイス管理、ローカル スクリプト、gp、sccm、mdm、intune
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 680171f2edc23b1d41a0665287c141e2a36d839e
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2021
ms.locfileid: "60150291"
---
# <a name="onboarding-tools-and-methods-for-windows-devices-in-defender-for-endpoint"></a>Defender for Endpoint のデバイスWindowsオンボーディング ツールとメソッド

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)
- [Microsoft 365エンドポイント データ損失防止 (DLP)](/microsoft-365/compliance/endpoint-dlp-learn-about)
- [Microsoft 365Insider リスク管理](/microsoft-365/compliance/insider-risk-management)

> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-assignaccess-abovefoldlink)

Defender for Endpoint サービスがセンサー データを取得できるよう、組織内のデバイスを構成する必要があります。 組織内のデバイスを構成するために使用できるさまざまな方法と展開ツールがあります。

次の展開ツールとメソッドがサポートされています。


トピック|説明
:---|:---
[グループ ポリシーを使用してデバイスをオンボードする](configure-endpoints-gp.md)|グループ ポリシーを使用して、構成パッケージをデバイスに展開します。
[Microsoft Endpoint Configuration Manager を使用したデバイスのオンボード](configure-endpoints-sccm.md)|Microsoft エンドポイント マネージャー (現在のブランチ) バージョン 1606 または Microsoft エンドポイント マネージャー (現在のブランチ) バージョン 1602 以前を使用して、デバイスに構成パッケージを展開できます。
[モバイル デバイス管理ツールを使用したデバイスのオンボード](configure-endpoints-mdm.md)|デバイスに構成パッケージを展開するには、Microsoft Intune管理ツールまたはモバイル デバイス管理ツールを使用します。
[ローカル スクリプトを使用したデバイスのオンボード](configure-endpoints-script.md)|ローカル スクリプトを使用してエンドポイントに構成パッケージを展開する方法について説明します。
[非永続的な仮想デスクトップ インフラストラクチャ (VDI) デバイスのオンボード](configure-endpoints-vdi.md)|構成パッケージを使用して VDI デバイスを構成する方法について説明します。

> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-configureendpoints-belowfoldlink)


デバイスのオンボード後、検出テストを実行して、デバイスがサービスに適切にオンボードされていることを確認できます。 詳細については、「新しくオンボードされた Microsoft Defender for Endpoint デバイスで検出テストを実行する [」を参照してください](run-detection-test.md)。