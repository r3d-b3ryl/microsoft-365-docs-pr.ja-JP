---
title: デバイスで検出テストを実行して、デバイスがMicrosoft Defender for Endpointに適切にオンボードされていることを確認します
description: Microsoft Defender for Endpoint サービスに最近オンボードされたデバイスで検出テスト スクリプトを実行して、適切に追加されていることを確認します。
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365-initiative-defender-endpoint
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 1d8459633d00d759fda1584e0084cd8ed4e12633
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2022
ms.locfileid: "64477261"
---
# <a name="run-a-detection-test-on-a-newly-onboarded-microsoft-defender-for-endpoint-device"></a>新しくオンボードされたMicrosoft Defender for Endpoint デバイスで検出テストを実行する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**
- Windows 11
- サポートされているWindows 10 バージョン
- Windows Server 2012 R2
- Windows Server 2016
- Windows Server バージョン 1803
- Windows Server 2019
- Windows Server 2022
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

管理のためにデバイスをMicrosoft Defender for Endpoint サービスに追加すると、これはオンボード デバイスとも呼ばれます。 オンボードを使用すると、デバイスは正常性状態に関するシグナルをサービスに報告できます。

デバイスがサービスに正常に追加されたことを確認または確認することは、デプロイ プロセス全体の重要なステップです。 これは、予想されるすべてのデバイスが管理されていることを保証します。 

## <a name="verify-microsoft-defender-for-endpoint-onboarding-of-a-device-using-a-powershell-detection-test"></a>PowerShell 検出テストMicrosoft Defender for Endpoint使用してデバイスのオンボードを確認する

新しくオンボードされたデバイスで次の PowerShell スクリプトを実行して、Defender for Endpoint サービスに正しく報告されていることを確認します。

1. 'C:\test-MDATP-test' というフォルダーを作成します。
2. デバイスで管理者特権のコマンド ライン プロンプトを開き、スクリプトを実行します。

   1. **[スタート]** をクリックし、「**cmd**」と入力します。

   1. **コマンド プロンプト** を右クリックし、[**管理者として実行**] を選択します。

      :::image type="content" source="images/run-as-admin.png" alt-text="管理者として実行を指すスタート メニュー" lightbox="images/run-as-admin.png":::
    
3. プロンプトで、次のコマンドをコピーして実行します。

   ```powershell
   powershell.exe -NoExit -ExecutionPolicy Bypass -WindowStyle Hidden $ErrorActionPreference = 'silentlycontinue';(New-Object System.Net.WebClient).DownloadFile('http://127.0.0.1/1.exe', 'C:\\test-MDATP-test\\invoice.exe');Start-Process 'C:\\test-MDATP-test\\invoice.exe'
   ```

コマンド プロンプト ウィンドウは自動的に閉じます。 成功した場合、オンボードされたデバイスの新しいアラートがポータルに約 10 分で表示されます。

## <a name="related-topics"></a>関連項目

- [Windows デバイスのオンボード](configure-endpoints.md)
- [オンボード サーバー](configure-server-endpoints.md)
- [Microsoft Defender for Endpoint の問題のトラブルシューティング](/microsoft-365/security/defender-endpoint/troubleshoot-onboarding)
