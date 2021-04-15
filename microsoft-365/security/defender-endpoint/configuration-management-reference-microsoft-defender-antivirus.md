---
title: ビジネスWindows Defender管理する
description: グループ ポリシー、Configuration Manager、PowerShell、WMI、Intune、およびコマンド ラインを使用して Microsoft Defender AV を管理する方法について説明します。
keywords: グループ ポリシー、gpo、config manager、sccm、scep、powershell、wmi、intune、Defender、ウイルス対策、マルウェア対策、セキュリティ、保護
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 12/16/2020
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 6b9845812763f9e3f1fdecf5566824eb76971dad
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2021
ms.locfileid: "51764869"
---
# <a name="manage-microsoft-defender-antivirus-in-your-business"></a>ビジネスで Microsoft Defender ウイルス対策を管理する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**

- [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)

次のツールを使用して、Microsoft Defender ウイルス対策を管理および構成できます。

- [Microsoft Intune](/mem/intune/protect/endpoint-security-antivirus-policy) (現在は Microsoft エンドポイント マネージャーの一部)
- [Microsoft Endpoint Configuration Manager](/mem/configmgr/protect/deploy-use/endpoint-protection-configure) (現在は Microsoft Endpoint Manager の一部)
- [グループ ポリシー](./use-group-policy-microsoft-defender-antivirus.md)
- [PowerShell コマンドレット](./use-powershell-cmdlets-microsoft-defender-antivirus.md)
- [Windows Management Instrumentation (WMI)](./use-wmi-microsoft-defender-antivirus.md)
- [Microsoft Malware Protection コマンド ライン ユーティリティ](./command-line-arguments-microsoft-defender-antivirus.md)(このユーティリティとmpcmdrun.exeされます。 

次の記事では、これらのツールを使用して Microsoft Defender Antivirus を管理および構成するための詳細な情報、リンク、およびリソースを提供します。

| 記事 | 説明 |
|:---|:---|
|[Microsoft Intune と Microsoft Endpoint Configuration Manager を使用して Microsoft Defender ウイルス対策を管理する](use-intune-config-manager-microsoft-defender-antivirus.md)|Intune と Configuration Manager を使用した Microsoft Defender ウイルス対策の展開、管理、レポート、構成に関する情報 |
|[グループ ポリシー設定を使用して Microsoft Defender ウイルス対策を管理する](use-group-policy-microsoft-defender-antivirus.md)|ADMX テンプレートにあるすべてのグループ ポリシー設定の一覧 |
|[PowerShell コマンドレットを使用して Microsoft Defender ウイルス対策を管理する](use-powershell-cmdlets-microsoft-defender-antivirus.md)|PowerShell コマンドレットを使用して Microsoft Defender ウイルス対策を管理する手順と、すべてのコマンドレットと許可されたパラメーターのドキュメントへのリンク |
|[Windows 管理インストルメンテーション (WMI) を使用して Microsoft Defender ウイルス対策を管理する](use-wmi-microsoft-defender-antivirus.md)| WMI を使用して Microsoft Defender ウイルス対策を管理する手順、および WMIv2 API のドキュメントへのリンク (すべてのクラス、メソッド、およびプロパティを含む) |
|[コマンド ライン ツールを使用して microsoft Defender ウイルスmpcmdrun.exeを管理する](command-line-arguments-microsoft-defender-antivirus.md)|専用のコマンド ライン ツールを使用して Microsoft Defender ウイルス対策を管理および使用する手順 |