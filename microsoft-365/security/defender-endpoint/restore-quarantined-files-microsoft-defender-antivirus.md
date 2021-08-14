---
title: Microsoft Defender AV で検疫済みファイルを復元する
description: Microsoft Defender AV によって検疫されたファイルとフォルダーを復元できます。
keywords: ''
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 05/20/2020
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: a07f43c11b1079bccb35a41c0ae913181be20d2d4f373a729e06ccf3b88a9045
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "53817701"
---
# <a name="restore-quarantined-files-in-microsoft-defender-av"></a>Microsoft Defender AV で検疫済みファイルを復元する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**

- [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)

デバイスMicrosoft Defender ウイルス対策脅威を検出して修復するように構成されている場合は、疑わしいMicrosoft Defender ウイルス対策を検疫します。 検疫済みファイルが脅威ではないと思う場合は、復元できます。

1. [ファイル **Windows セキュリティ] を開きます**。
2. [ **ウイルス対策&保護] を選択し、[** 保護の履歴] **をクリックします**。
3. 最近使用したアイテムの一覧で、[検疫済みアイテム **] をフィルター処理します**。
4. 保持するアイテムを選択し、復元などのアクションを実行します。

> [!TIP]
> 検疫からファイルを復元するには、コマンド プロンプトを使用することもできます。 「検疫 [からファイルを復元する」を参照してください](/windows/security/threat-protection/microsoft-defender-atp/respond-file-alerts#restore-file-from-quarantine)。 

## <a name="related-articles"></a>関連記事

- [スキャンの修復を構成する](configure-remediation-microsoft-defender-antivirus.md)
- [スキャン結果の確認](review-scan-results-microsoft-defender-antivirus.md)
- [ファイル名、拡張子、フォルダーの場所に基づいて除外を構成および検証する](configure-extension-file-exclusions-microsoft-defender-antivirus.md)
- [プロセスによって開いたファイルの除外を構成および検証する](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md)
- [サーバー Microsoft Defender ウイルス対策の除外をWindowsする](configure-server-exclusions-microsoft-defender-antivirus.md)