---
title: 新しくオンボードされた Microsoft Defender for Endpoint デバイスで検出テストを実行する
description: 新しくオンボードされたデバイスで検出スクリプトを実行して、Microsoft Defender for Endpoint サービスに正しくオンボードされていることを確認します。
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
ms.openlocfilehash: d73a07bdd57748a5756d0fabddeff3aee0cd4d5d
ms.sourcegitcommit: d817a3aecb700f7227a05cd165ffa7dbad67b09d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/29/2021
ms.locfileid: "53656285"
---
# <a name="run-a-detection-test-on-a-newly-onboarded-microsoft-defender-for-endpoint-device"></a>新しくオンボードされた Microsoft Defender for Endpoint デバイスで検出テストを実行する 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**
- サポートされているWindows 10バージョン
- Windows Server 2012 R2
- Windows Server 2016
- Windowsサーバー、バージョン 1803
- WindowsServer, 2019
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

新しくオンボードされたデバイスで次の PowerShell スクリプトを実行して、Defender for Endpoint サービスに適切に報告されていることを確認します。

1. フォルダーを作成する: 'C:\test-MDATP-test'。
2. デバイスで管理者特権のコマンド ライン プロンプトを開き、スクリプトを実行します。

   1. **[スタート]** をクリックし、「**cmd**」と入力します。

   1. [コマンド プロンプト] を **右クリックし、[** 管理者として **実行] を選択します**。

      ![[管理者スタート メニュー実行] をポイントするウィンドウ のウィンドウ](images/run-as-admin.png)

3. プロンプトで、次のコマンドをコピーして実行します。

   ```powershell
   powershell.exe -NoExit -ExecutionPolicy Bypass -WindowStyle Hidden $ErrorActionPreference = 'silentlycontinue';(New-Object System.Net.WebClient).DownloadFile('http://127.0.0.1/1.exe', 'C:\\test-MDATP-test\\invoice.exe');Start-Process 'C:\\test-MDATP-test\\invoice.exe'
   ```

[コマンド プロンプト] ウィンドウが自動的に閉じます。 成功した場合、検出テストは完了としてマークされ、約 10 分でオンボード デバイスのポータルに新しいアラートが表示されます。

## <a name="related-topics"></a>関連項目
- [Windows 10 デバイスのオンボード](configure-endpoints.md)
- [オンボード サーバー](configure-server-endpoints.md)
- [Microsoft Defender for Endpoint オンボーディングの問題のトラブルシューティング](/microsoft-365/security/defender-endpoint/troubleshoot-onboarding)
