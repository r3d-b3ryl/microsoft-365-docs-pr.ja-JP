---
title: Microsoft Defender ATP for Mac でのカーネル拡張機能の問題のトラブルシューティング
description: Microsoft Defender ATP for Mac のカーネル拡張機能に関連する問題のトラブルシューティングを行います。
keywords: microsoft、 defender, atp, mac, kernel, extension
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: bdd5c6309a19863339b00e846c1c2670fc4f261b
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187603"
---
# <a name="troubleshoot-kernel-extension-issues-in-microsoft-defender-for-endpoint-for-mac"></a>Microsoft Defender for Endpoint for Mac でのカーネル拡張機能の問題のトラブルシューティング

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**

- [Microsoft Defender for Endpoint for Mac](microsoft-defender-endpoint-mac.md)
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Microsoft Defender for Endpoint を体験してみませんか? [無料試用版にサインアップします。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

この記事では、Microsoft Defender for Endpoint for Mac の一部としてインストールされているカーネル拡張機能に関する問題をトラブルシューティングする方法について説明します。

macOS High Sierra (10.13) から、macOS では、デバイスでの実行を許可する前に、すべてのカーネル拡張機能を明示的に承認する必要があります。

Microsoft Defender for Endpoint for Mac の展開/インストール中にカーネル拡張機能を承認しなかった場合、アプリケーションはバナーを表示して有効にするように求めます。

   ![RTP が無効なスクリーンショット](/windows/security/threat-protection/microsoft-defender-antivirus/images/mdatp-32-main-app-fix)

また、実行できます ```mdatp health``` 。 リアルタイム保護が有効になっているが使用できない場合に報告されます。 これは、カーネル拡張機能がデバイスでの実行が承認されていないことを示します。

```bash
mdatp health
```
```Output
...
real_time_protection_enabled                : false
real_time_protection_available              : true
...
```

次のセクションでは、Microsoft Defender for Endpoint for Mac の展開に使用した方法に応じて、この問題に対処する方法に関するガイダンスを提供します。

## <a name="managed-deployment"></a>管理された展開

製品の展開に使用した管理ツールに対応する手順を参照してください。

- [JAMF ベースの展開](mac-install-with-jamf.md)
- [Microsoft Intune ベースの展開](mac-install-with-intune.md#create-system-configuration-profiles)

## <a name="manual-deployment"></a>手動展開

製品のインストールから 30 分未満経過した場合は **、[System Preferences** Security & Privacy] に移動し、開発者  >  "Microsoft Corporation" のシステム ソフトウェアを許可する必要があります。

このプロンプトが表示されない場合は、30 分以上経過し、カーネル拡張機能がデバイスでの実行が承認されていないことを意味します。

![プロンプトの有効期限が切れたスクリーンショットの後のセキュリティとプライバシーのウィンドウ](/windows/security/threat-protection/microsoft-defender-antivirus/images/mdatp-33-securityprivacysettings-noprompt)

この場合、承認フローを再度トリガーするには、次の手順を実行する必要があります。

1. ターミナルで、ドライバーのインストールを試みる。 カーネル拡張機能がデバイスでの実行を承認されていないので、次の操作は失敗します。 ただし、承認フローが再びトリガーされます。

    ```bash
    sudo kextutil /Library/Extensions/wdavkext.kext
    ```
    
    ```Output
    Kext rejected due to system policy: <OSKext 0x7fc34d528390 [0x7fffa74aa8e0]> { URL = "file:///Library/StagedExtensions/Library/Extensions/wdavkext.kext/", ID = "com.microsoft.wdavkext" }
    Kext rejected due to system policy: <OSKext 0x7fc34d528390 [0x7fffa74aa8e0]> { URL = "file:///Library/StagedExtensions/Library/Extensions/wdavkext.kext/", ID = "com.microsoft.wdavkext" }
    Diagnostics for /Library/Extensions/wdavkext.kext:
    ```

2. メニュー **から [System Preferences**  >  **Security &プライバシー]** を開きます。 (開いている場合は、最初に閉じます)。

3. **開発者** からのシステム ソフトウェアの許可 "Microsoft Corporation"

4. ターミナルで、ドライバーを再度インストールします。 この時間は、操作が成功します。

    ```bash
    sudo kextutil /Library/Extensions/wdavkext.kext
    ```

    バナーは Defender アプリケーションから消え、リアルタイム保護が有効で使用可能になっている ```mdatp health``` と報告する必要があります。

    ```bash
    mdatp health
    ```

    ```Output
    ...
    real_time_protection_enabled                : true
    real_time_protection_available              : true
    ...
    ```
