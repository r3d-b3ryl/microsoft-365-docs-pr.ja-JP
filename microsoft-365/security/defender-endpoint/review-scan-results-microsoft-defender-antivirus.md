---
title: Microsoft Defender ウイルス対策 スキャンの結果を確認する
description: Microsoft Endpoint Configuration Manager、Microsoft Intune、またはWindows セキュリティ アプリを使用してスキャンの結果を確認する
keywords: スキャン結果, 修復, フル スキャン, クイック スキャン
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 10/18/2021
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.collection: M365-security-compliance
ms.openlocfilehash: 9ffe10560bb36c8fc1311061510f35396934e3b8
ms.sourcegitcommit: 4f56b4b034267b28c7dd165e78ecfb4b5390087d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/12/2022
ms.locfileid: "64790638"
---
# <a name="review-microsoft-defender-antivirus-scan-results"></a>Microsoft Defender ウイルス対策スキャン結果を確認する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- Microsoft Defender ウイルス対策

**プラットフォーム**
- Windows

Microsoft Defender ウイルス対策 スキャンが完了すると、[オンデマンドスキャンでも](run-scan-microsoft-defender-antivirus.md)[スケジュールスキャン](scheduled-catch-up-scans-microsoft-defender-antivirus.md)でも、結果が記録され、結果を表示できます。 


## <a name="use-configuration-manager-to-review-scan-results"></a>Configuration Managerを使用してスキャン結果を確認する

[Endpoint Protection状態を監視する方法に関する](/configmgr/protect/deploy-use/monitor-endpoint-protection)ページを参照してください。

## <a name="use-powershell-cmdlets-to-review-scan-results"></a>PowerShell コマンドレットを使用してスキャン結果を確認する

次のコマンドレットは、エンドポイント上の各検出を返します。 同じ脅威の検出が複数ある場合、各検出の時刻に基づいて、各検出が個別に一覧表示されます。

```PowerShell
Get-MpThreatDetection
```

:::image type="content" source="../../media/wdav-get-mpthreatdetection.png" alt-text="PowerShell コマンドレットと出力" lightbox="../../media/wdav-get-mpthreatdetection.png":::

特定の脅威の検出のみを表示するように出力を制限するように指定 `-ThreatID` できます。

脅威の検出を一覧表示するが、同じ脅威の検出を 1 つの項目に結合する場合は、次のコマンドレットを使用できます。

```PowerShell
Get-MpThreat
```

:::image type="content" source="../../media/wdav-get-mpthreat.png" alt-text="PowerShell コード" lightbox="../../media/wdav-get-mpthreat.png":::

[Microsoft Defender ウイルス対策で PowerShell を使用する](use-powershell-cmdlets-microsoft-defender-antivirus.md)方法の詳細については、「PowerShell コマンドレットを使用してMicrosoft Defender ウイルス対策および [Defender ウイルス対策コマンドレット](/powershell/module/defender/)を構成して実行する」を参照してください。

## <a name="use-windows-management-instruction-wmi-to-review-scan-results"></a>Windows管理命令 (WMI) を使用してスキャン結果を確認する

[**MSFT_MpThreat** クラスと **MSFT_MpThreatDetection** クラスの **Get** メソッド](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)を使用します。

> [!TIP]
> 他のプラットフォームのウイルス対策関連情報を探している場合は、次を参照してください。
> - [macOS でMicrosoft Defender for Endpointの基本設定を設定する](mac-preferences.md)
> - [Mac 用 Microsoft Defender for Endpoint](microsoft-defender-endpoint-mac.md)
> - [IntuneのMicrosoft Defender ウイルス対策の macOS ウイルス対策ポリシー設定](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [Linux でMicrosoft Defender for Endpointの基本設定を設定する](linux-preferences.md)
> - [Linux 用 Microsoft Defender for Endpoint](microsoft-defender-endpoint-linux.md)
> - [Android の機能で Defender for Endpoint を構成する](android-configure.md)
> - [iOS 機能でMicrosoft Defender for Endpointを構成する](ios-configure-features.md)


## <a name="related-articles"></a>関連記事

- [Microsoft Defender ウイルス対策スキャンと修復の結果をカスタマイズ、開始、および確認する](customize-run-review-remediate-scans-microsoft-defender-antivirus.md)
- [Microsoft Defender ウイルス対策 (Windows 10)](microsoft-defender-antivirus-in-windows-10.md)
