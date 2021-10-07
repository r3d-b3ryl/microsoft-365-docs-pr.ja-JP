---
title: デバイスのオンボーディング方法Windows 10ツール
f1.keywords: NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: センサー Windows 10コンプライアンス ソリューションにセンサー データを送信できるよう、Microsoft 365デバイスをオンボードする
ms.openlocfilehash: f3f3e6a63b3761209a311ae45fcd20c8a9d786f0
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2021
ms.locfileid: "60203161"
---
# <a name="onboarding-tools-and-methods-for-windows-10-devices"></a>Windows 10 デバイスのオンボード ツールと各種方法

**適用対象:**
- [Microsoft 365エンドポイント データ損失防止 (DLP)](./endpoint-dlp-learn-about.md)

組織のデバイスは、エンドポイントデータ損失防止サービスMicrosoft 365センサー データを取得するように構成する必要があります。 組織内のデバイスを構成するために使用できるさまざまな方法と展開ツールがあります。

次の展開ツールとメソッドがサポートされています。

- グループ ポリシー
- Microsoft Endpoint Configuration Manager
- モバイル デバイスの管理 (Microsoft Intune を含む)
- ローカル スクリプト

## <a name="in-this-section"></a>このセクションの内容
トピック | 説明
:---|:---
[グループ ポリシー Windows 10デバイスのオンボード](dlp-configure-endpoints-gp.md) | グループ ポリシーを使用して、構成パッケージをデバイスに展開します。
[デバイスWindowsデバイスのオンボードMicrosoft Endpoint Configuration Manager](dlp-configure-endpoints-sccm.md) | Microsoft Endpoint Configuration Manager (現在のブランチ) バージョン 1606 または Microsoft Endpoint Configuration Manager (現在のブランチ) バージョン 1602 以前を使用して、デバイスに構成パッケージを展開できます。
[モバイル デバイス管理ツールを使用した Windows 10 デバイスのオンボード](dlp-configure-endpoints-mdm.md) | デバイスに構成パッケージを展開するには、Microsoft Intune管理ツールまたはモバイル デバイス管理ツールを使用します。
[ローカル スクリプトを使用した Windows 10 デバイスのオンボード](dlp-configure-endpoints-script.md) | ローカル スクリプトを使用してエンドポイントに構成パッケージを展開する方法について説明します。
[非永続的な仮想デスクトップ インフラストラクチャ (VDI) デバイスのオンボード](dlp-configure-endpoints-vdi.md) | 構成パッケージを使用して VDI デバイスを構成する方法について説明します。