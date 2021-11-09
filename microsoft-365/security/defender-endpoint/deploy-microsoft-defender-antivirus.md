---
title: Microsoft Defender ウイルス対策を展開して有効にする
description: ユーザー Microsoft Defender ウイルス対策、グループ ポリシー、PowerShell コマンドレット、または WMI をMicrosoft Intune、Microsoft Endpoint Configuration Managerエンドポイントを保護する方法を展開します。
keywords: 展開、有効化、Microsoft Defender ウイルス対策
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
ms.topic: conceptual
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.collection: m365-security-compliance
ms.openlocfilehash: 466254b9c59e1a005b588c1b61de236c37f3aa9f
ms.sourcegitcommit: e09ced3e3628bf2ccb84d205d9699483cbb4b3b0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/09/2021
ms.locfileid: "60882347"
---
# <a name="deploy-and-enable-microsoft-defender-antivirus"></a>Microsoft Defender ウイルス対策を展開して有効にする

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**

- [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)

使用している管理ツールによっては、保護を具体的に有効または構成する必要Microsoft Defender ウイルス対策があります。 

[Microsoft Intune、Microsoft Endpoint Configuration Manager、](deploy-manage-report-microsoft-defender-antivirus.md#ref2)グループ ポリシー、Active Directory、Microsoft Azure、PowerShell コマンドレット、Windows 管理命令 (WMI) による保護を有効にする方法については、「Microsoft Defender ウイルス対策 の展開、管理、およびレポート」の表を参照してください。

一部のシナリオでは、仮想デスクトップ インフラストラクチャ (VDI) 環境など、Microsoft Defender ウイルス対策保護を正常に展開または構成する方法に関するガイダンスが必要です。

このセクションの残りの記事では、VDI またはリモート デスクトップ サービス[(RDS)](deployment-vdi-microsoft-defender-antivirus.md)環境で仮想マシン (VM) で Microsoft Defender ウイルス対策 をセットアップするためのエンド to エンドのアドバイスとベスト プラクティスについて説明します。

## <a name="related-articles"></a>関連記事

- [Microsoft Defender ウイルス対策 (Windows 10)](microsoft-defender-antivirus-in-windows-10.md)
- [更新プログラムの展開、管理、およびレポートの作成Microsoft Defender ウイルス対策](deploy-manage-report-microsoft-defender-antivirus.md)
- [仮想デスクトップ インフラストラクチャ (VDI) 環境での Microsoft Defender ウイルス対策の展開ガイド](deployment-vdi-microsoft-defender-antivirus.md)