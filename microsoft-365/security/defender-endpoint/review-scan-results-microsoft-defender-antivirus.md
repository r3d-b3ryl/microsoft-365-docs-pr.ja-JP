---
title: スキャンの結果をMicrosoft Defender ウイルス対策する
description: アプリ、アプリ、またはアプリを使用Microsoft Endpoint Configuration Manager、Microsoft Intuneスキャンの結果Windows セキュリティする
keywords: スキャン結果、修復、フル スキャン、クイック スキャン
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 06/17/2021
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.collection: M365-security-compliance
ms.openlocfilehash: 76c865d7d95db34c2bb25cb2629e4cfee73cd022
ms.sourcegitcommit: 584445b62cb82218597b62495fb76fcb5b12af9d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2021
ms.locfileid: "59497826"
---
# <a name="review-microsoft-defender-antivirus-scan-results"></a>スキャンMicrosoft Defender ウイルス対策確認する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**

- [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)

オンデマンドスキャンMicrosoft Defender ウイルス対策、スケジュールされたスキャンの実行が完了すると、結果が[](run-scan-microsoft-defender-antivirus.md)記録され、結果[](scheduled-catch-up-scans-microsoft-defender-antivirus.md)を表示できます。 


## <a name="use-configuration-manager-to-review-scan-results"></a>Configuration Manager を使用してスキャン結果を確認する

詳細については[、「ユーザーの状態をEndpoint Protectionする」を参照してください](/configmgr/protect/deploy-use/monitor-endpoint-protection)。

## <a name="use-powershell-cmdlets-to-review-scan-results"></a>PowerShell コマンドレットを使用してスキャン結果を確認する

次のコマンドレットは、エンドポイント上の各検出を返します。 同じ脅威の複数の検出がある場合、各検出は、各検出の時間に基づいて個別に一覧表示されます。

```PowerShell
Get-MpThreatDetection
```

:::image type="content" source="../../media/wdav-get-mpthreatdetection.png" alt-text="PowerShell のコマンドレットと出力のスクリーンショット。":::

特定の `-ThreatID` 脅威に対する検出のみを表示する出力を制限する場合に指定できます。

脅威検出を一覧表示するが、同じ脅威の検出を 1 つのアイテムに結合する場合は、次のコマンドレットを使用できます。

```PowerShell
Get-MpThreat
```

:::image type="content" source="../../media/wdav-get-mpthreat.png" alt-text="PowerShell コード。":::

PowerShell[コマンドレットを](use-powershell-cmdlets-microsoft-defender-antivirus.md)構成して実行する方法の詳細については、「powerShell コマンドレットを使用して Microsoft Defender ウイルス対策 および[Defender](/powershell/module/defender/)コマンドレットを構成および実行する」を参照Microsoft Defender ウイルス対策。

## <a name="use-windows-management-instruction-wmi-to-review-scan-results"></a>スキャンWindows確認するには、管理命令 (WMI) を使用します。

クラスと [**クラス** の Get **メソッド** MSFT_MpThreat使用MSFT_MpThreatDetection](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)します。


## <a name="related-articles"></a>関連記事

- [スキャンと修復の結果をカスタマイズ、開始Microsoft Defender ウイルス対策確認する](customize-run-review-remediate-scans-microsoft-defender-antivirus.md)
- [Microsoft Defender ウイルス対策 (Windows 10)](microsoft-defender-antivirus-in-windows-10.md)