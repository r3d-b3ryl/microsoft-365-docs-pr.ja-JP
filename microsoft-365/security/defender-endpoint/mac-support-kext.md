---
title: macOS でのMicrosoft Defender for Endpointでのカーネル拡張機能の問題のトラブルシューティング
description: macOS でのMicrosoft Defender for Endpointでのカーネル拡張機能関連の問題のトラブルシューティングを行います。
keywords: microsoft、Defender、Microsoft Defender for Endpoint、mac、カーネル、拡張機能
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 72d1aab8be071b5f4ec66988b35655571625b409
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2022
ms.locfileid: "64477283"
---
# <a name="troubleshoot-kernel-extension-issues-in-microsoft-defender-for-endpoint-on-macos"></a>macOS でのMicrosoft Defender for Endpointでのカーネル拡張機能の問題のトラブルシューティング

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**

- [macOS 用 Microsoft Defender for Endpoint](microsoft-defender-endpoint-mac.md)
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

この記事では、macOS 上のMicrosoft Defender for Endpointの一部としてインストールされているカーネル拡張機能に関する問題をトラブルシューティングする方法について説明します。

macOS High Sierra (10.13) 以降では、macOS では、デバイスでの実行を許可する前にすべてのカーネル拡張機能を明示的に承認する必要があります。

macOS でのMicrosoft Defender for Endpointの展開/インストール中にカーネル拡張機能を承認しなかった場合は、アプリケーションにバナーが表示され、有効にするよう求められます。

:::image type="content" source="images/mdatp-32-main-app-fix.png" alt-text="RTP が無効になっている" lightbox="images/mdatp-32-main-app-fix.png":::

を実行 ```mdatp health```することもできます。 リアルタイム保護が有効になっているが使用できない場合はレポートされます。 これは、カーネル拡張機能がデバイスで実行することが承認されていないことを示します。

```bash
mdatp health
```
```Output
...
real_time_protection_enabled                : false
real_time_protection_available              : true
...
```

以降のセクションでは、macOS にMicrosoft Defender for Endpointを展開するために使用した方法に応じて、この問題に対処する方法に関するガイダンスを提供します。

## <a name="managed-deployment"></a>管理された展開

製品のデプロイに使用した管理ツールに対応する手順を参照してください。

- [JAMF ベースのデプロイ](mac-install-with-jamf.md)
- [Microsoft Intune ベースの展開](mac-install-with-intune.md#create-system-configuration-profiles)

## <a name="manual-deployment"></a>手動展開

製品のインストールから 30 分未満の場合は、 **System Preferences** \> **Security & Privacy** に移動します。ここで、開発者 "Microsoft Corporation" のシステム ソフトウェアを **許可** する必要があります。

このプロンプトが表示されない場合は、30 分以上経過し、カーネル拡張機能がデバイスで実行することが承認されていないことを意味します。

:::image type="content" source="images/mdatp-33-securityprivacysettings-noprompt.png" alt-text="プロンプトの有効期限が切れた後のセキュリティとプライバシーのウィンドウ" lightbox="images/mdatp-33-securityprivacysettings-noprompt.png":::

この場合、承認フローを再度トリガーするには、次の手順を実行する必要があります。

1. ターミナルで、ドライバーのインストールを試みます。 カーネル拡張機能がデバイスで実行することが承認されていないため、次の操作は失敗します。 ただし、承認フローが再度トリガーされます。

    ```bash
    sudo kextutil /Library/Extensions/wdavkext.kext
    ```

    ```Output
    Kext rejected due to system policy: <OSKext 0x7fc34d528390 [0x7fffa74aa8e0]> { URL = "file:///Library/StagedExtensions/Library/Extensions/wdavkext.kext/", ID = "com.microsoft.wdavkext" }
    Kext rejected due to system policy: <OSKext 0x7fc34d528390 [0x7fffa74aa8e0]> { URL = "file:///Library/StagedExtensions/Library/Extensions/wdavkext.kext/", ID = "com.microsoft.wdavkext" }
    Diagnostics for /Library/Extensions/wdavkext.kext:
    ```

2. メニューから **システム環境設定の** \> **セキュリティ&プライバシー** を開きます。 (開いている場合は、最初に閉じます。

3. 開発者 "Microsoft Corporation" からシステム ソフトウェアを **許可する**

4. ターミナルで、ドライバーをもう一度インストールします。 この時点で、操作は成功します。

    ```bash
    sudo kextutil /Library/Extensions/wdavkext.kext
    ```

    バナーは Defender アプリケーションから消え、 ```mdatp health``` リアルタイム保護が有効で使用可能であることを報告する必要があります。

    ```bash
    mdatp health
    ```

    ```Output
    ...
    real_time_protection_enabled                : true
    real_time_protection_available              : true
    ...
    ```
