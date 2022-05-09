---
title: Microsoft Defender ウイルス対策で検疫済みファイルを復元する
description: Microsoft Defender ウイルス対策によって検疫されたファイルとフォルダーを復元できます。
keywords: ''
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 10/19/2021
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.collection: M365-security-compliance
ms.openlocfilehash: 14b6f6812e88a49220230e0e422d5c95f90fe187
ms.sourcegitcommit: 4f56b4b034267b28c7dd165e78ecfb4b5390087d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/12/2022
ms.locfileid: "64790594"
---
# <a name="restore-quarantined-files-in-microsoft-defender-antivirus"></a>Microsoft Defender ウイルス対策で検疫済みファイルを復元する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- Microsoft Defender ウイルス対策

**プラットフォーム**
- Windows

デバイス上の脅威を検出して修復するようにMicrosoft Defender ウイルス対策が構成されている場合は、疑わしいファイルを検疫Microsoft Defender ウイルス対策。 検疫されたファイルが脅威でないと確信している場合は、復元できます。

1. **Windows セキュリティ** を開きます。
2. **[ウイルス&脅威の防止**] を選択し、[**保護の履歴**] をクリックします。
3. 最近のすべての項目の一覧で、 **検疫済みアイテム** をフィルター処理します。
4. 保持する項目を選択し、復元などのアクションを実行します。

> [!TIP]
> コマンド プロンプトを使用して、検疫からファイルを復元することもできます。 [「検疫からファイルを復元する」を](/windows/security/threat-protection/microsoft-defender-atp/respond-file-alerts#restore-file-from-quarantine)参照してください。 

> [!TIP]
> 他のプラットフォームのウイルス対策関連情報を探している場合は、次を参照してください。
> - [macOS 上で Microsoft Defender for Endpoint 用の基本設定を設定する](mac-preferences.md)
> - [Mac 用 Microsoft Defender for Endpoint](microsoft-defender-endpoint-mac.md)
> - [Intune の Microsoft Defender ウイルス対策の macOS ウイルス対策ポリシー設定](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [Linux 上で Microsoft Defender for Endpoint 用の基本設定を設定する](linux-preferences.md)
> - [Linux 用 Microsoft Defender for Endpoint](microsoft-defender-endpoint-linux.md)
> - [Android 機能用 Defender for Endpoint を構成する](android-configure.md)
> - [iOS 機能用 Microsoft Defender for Endpoint を構成する](ios-configure-features.md)

## <a name="related-articles"></a>関連記事

- [スキャンの修復を構成する](configure-remediation-microsoft-defender-antivirus.md)
- [スキャン結果を確認する](review-scan-results-microsoft-defender-antivirus.md)
- [ファイル名、拡張子、フォルダーの場所に基づいて除外を構成および検証する](configure-extension-file-exclusions-microsoft-defender-antivirus.md)
- [プロセスによって開かれたファイルの除外を構成して検証する](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md)
- [Windows サーバーでMicrosoft Defender ウイルス対策除外を構成する](configure-server-exclusions-microsoft-defender-antivirus.md)