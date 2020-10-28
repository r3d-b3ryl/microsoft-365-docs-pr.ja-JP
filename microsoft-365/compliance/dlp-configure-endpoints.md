---
title: Windows 10 デバイスのオンボードツールおよび方法 (プレビュー)
f1.keywords: NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: Microsoft 365 コンプライアンスソリューションにセンサーデータを送信できるように、Windows 10 デバイスをオンボードにします。
ms.openlocfilehash: 5f5a777d11dda900116b6095166ffffed6efa31b
ms.sourcegitcommit: bd36c88e731e3fee2a3a5cb3564fdc94f11bab94
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769644"
---
# <a name="onboarding-tools-and-methods-for-windows-10-devices-preview"></a>Windows 10 デバイスのオンボードツールおよび方法 (プレビュー)

**適用対象:**
- [Microsoft 365 エンドポイントのデータ損失防止 (DLP)](/microsoft-365/compliance/endpoint-dlp-learn-about)

組織内のデバイスは、Microsoft 365 エンドポイントデータ損失防止サービスがそれらからセンサーデータを取得できるように構成する必要があります。 組織内のデバイスの構成に使用できるさまざまな方法と展開ツールがあります。

次の展開ツールと方法がサポートされています。

- グループポリシー
- Microsoft Endpoint Configuration Manager
- モバイルデバイス管理 (Microsoft Intune を含む)
- ローカルスクリプト

## <a name="in-this-section"></a>このセクションの内容
トピック | 説明
:---|:---
[グループポリシーを使用した Windows 10 デバイスのオンボード](dlp-configure-endpoints-gp.md) | グループポリシーを使用して、構成パッケージをデバイスに展開します。
[Microsoft エンドポイント構成マネージャーを使用した Windows デバイスのオンボード](dlp-configure-endpoints-sccm.md) | 構成パッケージをデバイスに展開するには、Microsoft エンドポイント構成マネージャー (current branch) バージョン1606または Microsoft エンドポイント構成マネージャー (current branch) version 1602 またはそれ以前のバージョンを使用できます。
[モバイルデバイス管理ツールを使用した Windows 10 デバイスのオンボード](dlp-configure-endpoints-mdm.md) | モバイルデバイス管理ツールまたは Microsoft Intune を使用して、構成パッケージをデバイスに展開します。
[ローカルスクリプトを使用した Windows 10 デバイスのオンボード](dlp-configure-endpoints-script.md) | ローカルスクリプトを使用して構成パッケージをエンドポイントに展開する方法について説明します。
[オンボードの非永続仮想デスクトップインフラストラクチャ (VDI) デバイス](dlp-configure-endpoints-vdi.md) | 構成パッケージを使用して VDI デバイスを構成する方法について説明します。
