---
title: スケジュールされたスキャンとオンデマンド スキャンを実行してカスタマイズします。
description: ネットワーク全体のエンドポイントMicrosoft Defender ウイルス対策スキャンをカスタマイズして開始する
keywords: スキャン、スケジュール、カスタマイズ、除外、ファイルの除外、修復、スキャン結果、検疫、脅威の削除、クイック スキャン、フル スキャン、Microsoft Defender ウイルス対策
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.collection: M365-security-compliance
ms.openlocfilehash: 63630c5a255e009a3fabaa0f2db168ded0e2c3c1
ms.sourcegitcommit: 6968594dc8cf8b30a4c958df6d65dfd0cd2cfae1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2021
ms.locfileid: "59490203"
---
# <a name="customize-initiate-and-review-the-results-of-microsoft-defender-antivirus-scans-and-remediation"></a>スキャンと修復の結果をカスタマイズ、開始Microsoft Defender ウイルス対策確認する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**

- [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)

グループ ポリシー、PowerShell、および Windows管理インストルメンテーション (WMI) を使用して、Microsoft Defender ウイルス対策できます。 

## <a name="in-this-section"></a>このセクションの内容

トピック | 説明
---|---
[ファイル、フォルダー、およびプロセスで開いたファイルの除外の構成と検証を行い、Microsoft Defender ウイルス対策します。](configure-exclusions-microsoft-defender-antivirus.md) | ファイル (指定されたプロセスによって変更されたファイルを含む) とフォルダーを、オンデマンド スキャン、スケジュールされたスキャン、および常時オンのリアルタイム保護監視とスキャンから除外できます。
[Microsoft Defender ウイルス対策スキャン オプションを構成する](configure-advanced-scan-types-microsoft-defender-antivirus.md) | 特定の種類のMicrosoft Defender ウイルス対策、バックアップまたは再解析ポイント、およびアーカイブ されたファイル (.zip ファイルなど) をスキャンに含めるには、Microsoft Defender ウイルス対策 を構成できます。 ネットワーク ファイルのスキャンを有効にできます
[スキャンの修復を構成する](configure-remediation-microsoft-defender-antivirus.md) | 脅威をMicrosoft Defender ウイルス対策するときに実行する必要がある操作と、検疫フォルダーに検疫されたファイルを保持する期間を構成する
[スケジュールされたスキャンを構成する](scheduled-catch-up-scans-microsoft-defender-antivirus.md) | 定期的な (スケジュールされた) スキャンのセットアップ (実行する必要がある場合、フル スキャンとクイック スキャンの実行のかどうかなど)
[スキャンの構成と実行](run-scan-microsoft-defender-antivirus.md) | PowerShell、Windows 管理インストルメンテーション、またはアプリを使用してエンドポイントで個別にオンデマンド スキャンを実行Windows セキュリティする
[スキャン結果の確認](review-scan-results-microsoft-defender-antivirus.md) | アプリ、アプリ、またはアプリを使用Microsoft Endpoint Configuration Manager、Microsoft Intuneスキャンの結果Windows セキュリティする