---
title: ライブ応答の問題Microsoft Defender for Endpointトラブルシューティングする
description: Microsoft Defender for Endpointでライブ応答を使用するときに発生する可能性がある問題のトラブルシューティング
keywords: ライブ応答、ライブ、応答、ロック、ファイルのトラブルシューティング
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: troubleshooting
ms.technology: mde
ms.openlocfilehash: c6a2f676839caefc34b9dff03f860d04a260de0c
ms.sourcegitcommit: d09eb780dc41a01796eb8137fbe9267231af6746
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/19/2022
ms.locfileid: "67384940"
---
# <a name="troubleshoot-microsoft-defender-for-endpoint-live-response-issues"></a>ライブ応答の問題Microsoft Defender for Endpointトラブルシューティングする

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-pullalerts-abovefoldlink)

このページでは、ライブ応答の問題をトラブルシューティングするための詳細な手順について説明します。

## <a name="file-cannot-be-accessed-during-live-response-sessions"></a>ライブ応答セッション中にファイルにアクセスできない

ライブ応答セッション中にアクションを実行しようとすると、ファイルにアクセスできないことを示すエラー メッセージが表示される場合は、次の手順を使用して問題に対処する必要があります。

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

2. ライブ応答ライブラリにスクリプトを追加します。
3. コピーするファイルのファイル パスという 1 つのパラメーターを指定してスクリプトを実行します。
4. TEMP フォルダーに移動します。
5. コピーしたファイルに対して実行するアクションを実行します。

## <a name="slow-live-response-sessions-or-delays-during-initial-connections"></a>ライブ応答セッションが遅い、または初期接続中に遅延が発生する

ライブ応答では、Windows の WNS サービスに対する Defender for Endpoint センサーの登録が利用されます。 ライブ応答で接続の問題が発生している場合は、次の詳細を確認します。

1. `notify.windows.com` は環境でブロックされません。 詳細については、「 [デバイス プロキシとインターネット接続の設定を構成する](configure-proxy-internet.md#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server)」を参照してください。
2. WpnService (Windows プッシュ通知システム サービス) は無効ではありません。
3. WNS クラウドとの WpnService 接続は、グループ ポリシーまたは MDM 設定では無効になりません。 ['通知ネットワークの使用状況をオフにする'](/windows/client-management/mdm/policy-csp-notifications) は '1' に設定しないでください。

WpnService サービスの動作と要件を完全に理解するには、以下の記事を参照してください。

- [Windows プッシュ通知サービス (WNS) の概要](/windows/uwp/design/shell/tiles-and-notifications/windows-push-notification-services--wns--overview)
- [WNS トラフィックをサポートするためのエンタープライズ ファイアウォールとプロキシ構成](/windows/uwp/design/shell/tiles-and-notifications/firewall-allowlist-config)
- [Microsoft プッシュ通知サービス (MPNS) パブリック IP 範囲](https://www.microsoft.com/download/details.aspx?id=44535)
