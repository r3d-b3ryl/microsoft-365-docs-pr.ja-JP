---
title: Microsoft Defender for Endpoint のライブ応答の問題のトラブルシューティング
description: Microsoft Defender for Endpoint でライブ応答を使用するときに発生する可能性のある問題のトラブルシューティング
keywords: ライブ応答、ライブ、応答、ロック、ファイルのトラブルシューティング
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
ms.collection: M365-security-compliance
ms.topic: troubleshooting
ms.technology: mde
ms.openlocfilehash: 0b64c38ac19e692fd0580c42aa89116f8c0f3421
ms.sourcegitcommit: f88a0ec621e7d9bc5f376eeaf70c8a9800711f88
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/15/2021
ms.locfileid: "59353670"
---
# <a name="troubleshoot-microsoft-defender-for-endpoint-live-response-issues"></a>Microsoft Defender for Endpoint のライブ応答の問題のトラブルシューティング

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-pullalerts-abovefoldlink)

このページでは、ライブ応答の問題をトラブルシューティングするための詳細な手順を示します。

## <a name="file-cannot-be-accessed-during-live-response-sessions"></a>ライブ応答セッション中にファイルにアクセスできない

ライブ応答セッション中にアクションを実行しようとしている場合は、ファイルにアクセスできないというエラー メッセージが表示される場合は、以下の手順を使用して問題に対処する必要があります。

1. 次のスクリプト コード スニペットをコピーし、PS1 ファイルとして保存します。

    ```powershell
    $copied_file_path=$args[0]
    $action=Copy-Item $copied_file_path -Destination $env:TEMP -PassThru -ErrorAction silentlyContinue

    if ($action){
         Write-Host "You copied the file specified in $copied_file_path to $env:TEMP Succesfully"
    }

    else{
        Write-Output "Error occoured while trying to copy a file, details:"
        Write-Output  $error[0].exception.message

    }
    ```

2. スクリプトをライブ応答ライブラリに追加します。
3. コピーするファイルのファイル パスという 1 つのパラメーターでスクリプトを実行します。
4. TEMP フォルダーに移動します。
5. コピーしたファイルに対して実行するアクションを実行します。

## <a name="slow-live-response-sessions-or-delays-during-initial-connections"></a>ライブ応答セッションが遅い、または初期接続中の遅延

ライブ応答では、Defender for Endpoint センサーの登録と WNS サービスWindows。 ライブ応答で接続の問題が発生している場合は、次の詳細を確認します。

1. `notify.windows.com` 環境でブロックされません。 詳細については、「デバイス プロキシと [インターネット接続の設定を構成する」を参照してください](configure-proxy-internet.md#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server)。
2. WpnService (Windowsプッシュ通知システム サービス) は無効ではありません。

WpnService サービスの動作と要件を完全に理解するには、以下の記事を参照してください。

- [Windowsプッシュ Notification Services (WNS) の概要](/windows/uwp/design/shell/tiles-and-notifications/windows-push-notification-services--wns--overview)
- [EnterpriseWNS トラフィックをサポートするファイアウォールとプロキシの構成](/windows/uwp/design/shell/tiles-and-notifications/firewall-allowlist-config)
- [Microsoft プッシュ通知サービス (MPNS) パブリック IP 範囲](https://www.microsoft.com/download/details.aspx?id=44535)
