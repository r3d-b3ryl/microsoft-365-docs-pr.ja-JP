---
title: Microsoft Defender AV スキャンの結果を確認する
description: Microsoft Endpoint Configuration Manager、Microsoft Intune、または Windows セキュリティ アプリを使用してスキャンの結果を確認する
keywords: スキャン結果、修復、フル スキャン、クイック スキャン
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/28/2020
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 3b8a299f41541be878a9e9023ab330ea973646fd
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2021
ms.locfileid: "51764147"
---
# <a name="review-microsoft-defender-antivirus-scan-results"></a>Microsoft Defender ウイルス対策スキャンの結果を確認する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**

- [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)

Microsoft Defender ウイルス対策スキャンが完了すると、オンデマンド スキャン[](run-scan-microsoft-defender-antivirus.md)でもスケジュールスキャンでも[](scheduled-catch-up-scans-microsoft-defender-antivirus.md)、結果が記録され、結果を表示できます。 


## <a name="use-configuration-manager-to-review-scan-results"></a>Configuration Manager を使用してスキャン結果を確認する

「 [エンドポイント保護の状態を監視する方法」を参照してください](/configmgr/protect/deploy-use/monitor-endpoint-protection)。

## <a name="use-powershell-cmdlets-to-review-scan-results"></a>PowerShell コマンドレットを使用してスキャン結果を確認する

次のコマンドレットは、エンドポイント上の各検出を返します。 同じ脅威の複数の検出がある場合、各検出は、各検出の時間に基づいて個別に一覧表示されます。

```PowerShell
Get-MpThreatDetection
```

![PowerShell コマンドレットと出力のスクリーンショット](images/defender/wdav-get-mpthreatdetection.png)

特定の `-ThreatID` 脅威に対する検出のみを表示する出力を制限する場合に指定できます。

脅威検出を一覧表示するが、同じ脅威の検出を 1 つのアイテムに結合する場合は、次のコマンドレットを使用できます。

```PowerShell
Get-MpThreat
```

![PowerShell のスクリーンショット](images/defender/wdav-get-mpthreat.png)

[Microsoft Defender ウイルス対策で PowerShell](use-powershell-cmdlets-microsoft-defender-antivirus.md)を使用する方法の詳細については、「Use PowerShell コマンドレットを使用して Microsoft Defender Antivirus コマンドレットと[Defender](/powershell/module/defender/)コマンドレットを構成および実行する」を参照してください。

## <a name="use-windows-management-instruction-wmi-to-review-scan-results"></a>Windows 管理命令 (WMI) を使用してスキャン結果を確認する

クラスと [**クラス** の Get **メソッド** MSFT_MpThreat使用MSFT_MpThreatDetection](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)します。


## <a name="related-articles"></a>関連記事

- [Microsoft Defender ウイルス対策スキャンと修復の結果をカスタマイズ、開始、および確認する](customize-run-review-remediate-scans-microsoft-defender-antivirus.md)
- [Windows 10 の Microsoft Defender ウイルス対策](microsoft-defender-antivirus-in-windows-10.md)