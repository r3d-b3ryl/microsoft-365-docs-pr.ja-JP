---
title: スケジュールされたスキャンとオンデマンド スキャンの実行とカスタマイズ
description: ネットワーク全体のエンドポイントで Microsoft Defender ウイルス対策スキャンをカスタマイズして開始します。
keywords: スキャン、スケジュール、カスタマイズ、除外、ファイルの除外、修復、スキャン結果、検疫、脅威の削除、クイック スキャン、フル スキャン、Microsoft Defender Antivirus
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 115a8ee56ca5e9768b3aba11c37f8423ef31a67b
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2021
ms.locfileid: "51765697"
---
# <a name="customize-initiate-and-review-the-results-of-microsoft-defender-antivirus-scans-and-remediation"></a>Microsoft Defender ウイルス対策スキャンと修復の結果をカスタマイズ、開始、および確認する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**

- [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)

グループ ポリシー、PowerShell、および Windows 管理インストルメンテーション (WMI) を使用して、Microsoft Defender ウイルス対策スキャンを構成できます。 

## <a name="in-this-section"></a>このセクションの内容

トピック | 説明
---|---
[Microsoft Defender ウイルス対策スキャンでファイル、フォルダー、およびプロセスで開いたファイルの除外を構成および検証する](configure-exclusions-microsoft-defender-antivirus.md) | ファイル (指定されたプロセスによって変更されたファイルを含む) とフォルダーを、オンデマンド スキャン、スケジュールされたスキャン、および常時オンのリアルタイム保護監視とスキャンから除外できます。
[Microsoft Defender ウイルス対策スキャン オプションの構成](configure-advanced-scan-types-microsoft-defender-antivirus.md) | Microsoft Defender ウイルス対策を構成して、特定の種類の電子メール ストレージ ファイル、バックアップまたは再解析ポイント、およびアーカイブ ファイル (.zip ファイルなど) をスキャンに含めます。 ネットワーク ファイルのスキャンを有効にできます
[スキャンの修復を構成する](configure-remediation-microsoft-defender-antivirus.md) | 脅威を検出した場合の Microsoft Defender ウイルス対策の実行方法と、検疫フォルダーに検疫されたファイルを保持する期間を構成する
[スケジュールされたスキャンを構成する](scheduled-catch-up-scans-microsoft-defender-antivirus.md) | 定期的な (スケジュールされた) スキャンのセットアップ (実行する必要がある場合、フル スキャンとクイック スキャンの実行のかどうかなど)
[スキャンの構成と実行](run-scan-microsoft-defender-antivirus.md) | PowerShell、Windows 管理インストルメンテーション、または Windows セキュリティ アプリを使用してエンドポイントで個別にオンデマンド スキャンを実行および構成する
[スキャン結果の確認](review-scan-results-microsoft-defender-antivirus.md) | Microsoft Endpoint Configuration Manager、Microsoft Intune、または Windows セキュリティ アプリを使用してスキャンの結果を確認する