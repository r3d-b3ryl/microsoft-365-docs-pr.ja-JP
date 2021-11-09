---
title: Microsoft Defender ウイルス対策で検疫済みファイルを復元する
description: ユーザーが検疫したファイルとフォルダーを復元Microsoft Defender ウイルス対策。
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
ms.openlocfilehash: a1e5926233d5e1e86101d2f22dfe3e149746a120
ms.sourcegitcommit: e09ced3e3628bf2ccb84d205d9699483cbb4b3b0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/09/2021
ms.locfileid: "60884027"
---
# <a name="restore-quarantined-files-in-microsoft-defender-antivirus"></a>Microsoft Defender ウイルス対策で検疫済みファイルを復元する

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