---
title: Microsoft Defender ウイルス対策の展開と有効化
description: Microsoft Intune、Microsoft Endpoint Configuration Manager、グループ ポリシー、PowerShell コマンドレット、WMI を使用してエンドポイントを保護するために Microsoft Defender ウイルス対策を展開します。
keywords: 展開、有効、Microsoft Defender ウイルス対策
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 01/06/2021
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 146447f4036d800832c75c7a59978e9571253a17
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2021
ms.locfileid: "51764821"
---
# <a name="deploy-and-enable-microsoft-defender-antivirus"></a>Microsoft Defender ウイルス対策の展開と有効化

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**

- [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)

使用している管理ツールによっては、Microsoft Defender ウイルス対策保護を具体的に有効または構成する必要がある場合があります。 

Microsoft Intune、Microsoft Endpoint Configuration Manager、グループ ポリシー、Active Directory、Microsoft Azure、PowerShell コマンドレット、および Windows 管理命令 (WMI) による保護を有効にする方法については [、「Microsoft Defender ウイルス](deploy-manage-report-microsoft-defender-antivirus.md#ref2) 対策の展開、管理、およびレポート」の表を参照してください。

一部のシナリオでは、仮想デスクトップ インフラストラクチャ (VDI) 環境など、Microsoft Defender ウイルス対策保護を正常に展開または構成する方法に関するガイダンスが必要です。

このセクションの残りの記事では、VDI またはリモート デスクトップ サービス [(RDS)](deployment-vdi-microsoft-defender-antivirus.md)環境で仮想マシン (VM) で Microsoft Defender ウイルス対策をセットアップするためのエンド to エンドのアドバイスとベスト プラクティスについて説明します。

## <a name="related-articles"></a>関連記事

- [Windows 10 の Microsoft Defender ウイルス対策](microsoft-defender-antivirus-in-windows-10.md)
- [Microsoft Defender Antivirus での更新プログラムの展開、管理、レポートの作成](deploy-manage-report-microsoft-defender-antivirus.md)
- [仮想デスクトップ インフラストラクチャ (VDI) 環境での Microsoft Defender ウイルス対策の展開ガイド](deployment-vdi-microsoft-defender-antivirus.md)