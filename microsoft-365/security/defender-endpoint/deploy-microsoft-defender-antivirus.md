---
title: Microsoft Defender ウイルス対策を展開して有効にする
description: Microsoft Intune、Microsoft Endpoint Configuration Manager、グループ ポリシー、PowerShell コマンドレット、または WMI を使用してエンドポイントを保護するためのMicrosoft Defender ウイルス対策をデプロイします。
keywords: デプロイ、有効化、Microsoft Defender ウイルス対策
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
ms.openlocfilehash: f3ab5a838945121a9c46a5448dbaec7bfa06b4c5
ms.sourcegitcommit: ebbe8713297675db5dcb3e0d9c3ae5e746b99196
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2022
ms.locfileid: "65419068"
---
# <a name="deploy-and-enable-microsoft-defender-antivirus"></a>Microsoft Defender ウイルス対策を展開して有効にする

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**

- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- Microsoft Defender ウイルス対策

**プラットフォーム**
- Windows

使用している管理ツールによっては、Microsoft Defender ウイルス対策保護を具体的に有効または構成する必要がある場合があります。 

[Microsoft Intune、Microsoft Endpoint Configuration Manager、グループ ポリシー、](deploy-manage-report-microsoft-defender-antivirus.md#ref2)Active を使用して保護を有効にする方法については、「Microsoft Defender ウイルス対策のデプロイ、管理、レポート」の表を参照してください。ディレクトリ、Microsoft Azure、PowerShell コマンドレット、およびWindows管理命令 (WMI)。

一部のシナリオでは、Virtual Desktop Infrastructure (VDI) 環境など、Microsoft Defender ウイルス対策保護を正常にデプロイまたは構成する方法に関するより多くのガイダンスが必要です。

このセクションの残りの記事では、[VDI またはリモート デスクトップ サービス (RDS) 環境で仮想マシン (VM) にMicrosoft Defender ウイルス対策を設定](deployment-vdi-microsoft-defender-antivirus.md)するためのエンド ツー エンドのアドバイスとベスト プラクティスについて説明します。

## <a name="related-articles"></a>関連記事

- [Microsoft Defender ウイルス対策 (Windows 10)](microsoft-defender-antivirus-in-windows-10.md)
- [更新プログラムのデプロイ、管理、Microsoft Defender ウイルス対策に関するレポート](deploy-manage-report-microsoft-defender-antivirus.md)
- [仮想デスクトップ インフラストラクチャ (VDI) 環境での Microsoft Defender ウイルス対策の展開ガイド](deployment-vdi-microsoft-defender-antivirus.md)

> [!TIP]
> 他のプラットフォームのウイルス対策関連情報を探している場合は、次を参照してください。
> - [macOS 上で Microsoft Defender for Endpoint 用の基本設定を設定する](mac-preferences.md)
> - [Mac 用 Microsoft Defender for Endpoint](microsoft-defender-endpoint-mac.md)
> - [Intune の Microsoft Defender ウイルス対策の macOS ウイルス対策ポリシー設定](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [Linux 上で Microsoft Defender for Endpoint 用の基本設定を設定する](linux-preferences.md)
> - [Linux 用 Microsoft Defender for Endpoint](microsoft-defender-endpoint-linux.md)
> - [Android 機能用 Defender for Endpoint を構成する](android-configure.md)
> - [iOS 機能用 Microsoft Defender for Endpoint を構成する](ios-configure-features.md)