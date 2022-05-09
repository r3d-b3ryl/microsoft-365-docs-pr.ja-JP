---
title: ライブ応答を使用してMicrosoft Defender for Endpointでサポート ログを収集する
description: ライブ応答を使用してログを収集し、Microsoft Defender for Endpointの問題をトラブルシューティングする方法について説明します
keywords: サポート, ログ, 収集, トラブルシューティング, ライブ応答, liveanalyzer, analyzer, live, response
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
ms.openlocfilehash: 138b532e7786a3d142c3cbbe68f668a4b0e05591
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2022
ms.locfileid: "64472575"
---
# <a name="collect-support-logs-in-microsoft-defender-for-endpoint-using-live-response"></a>ライブ応答を使用してMicrosoft Defender for Endpointでサポート ログを収集する


**適用対象:**
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-pullalerts-abovefoldlink)


サポートに問い合わせるときに、Microsoft Defender for Endpoint Client Analyzer ツールの出力パッケージを指定するように求められる場合があります。

このトピックでは、Live Response を使用してツールを実行する方法について説明します。

1. [Microsoft Defender for Endpoint クライアント アナライザー](https://aka.ms/BetaMDEAnalyzer)の 'Tools' サブディレクトリ内から使用可能な必要なスクリプトをダウンロードしてフェッチします。 <br>
たとえば、基本的なセンサーとデバイスの正常性ログを取得するには、".. をフェッチします。\Tools\MDELiveAnalyzer.ps1」<br>
Defender ウイルス対策のサポート ログ (MpSupportFiles.cab) も必要な場合は、".. をフェッチします。\Tools\MDELiveAnalyzerAV.ps1" 

2. 調査する必要があるコンピューターで [Live Response セッション](live-response.md#initiate-a-live-response-session-on-a-device) を開始します。

3. **ライブラリアップロードファイルを選択します**。

   :::image type="content" source="images/upload-file.png" alt-text="アップロード ファイル" lightbox="images/upload-file.png":::

4. [ **ファイルの選択] を選択します**。

   :::image type="content" source="images/choose-file.png" alt-text="[ファイルの選択] ボタン -1" lightbox="images/choose-file.png":::

5. MDELiveAnalyzer.ps1という名前のダウンロードしたファイルを選択し、[**確認**] をクリックします。

   :::image type="content" source="images/analyzer-file.png" alt-text="[ファイルの選択] ボタン -2" lightbox="images/analyzer-file.png":::

6. LiveResponse セッション中は、次のコマンドを使用してアナライザーを実行し、結果ファイルを収集します。

    ```console
    Run MDELiveAnalyzer.ps1
    GetFile "C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Downloads\MDEClientAnalyzerResult.zip"
    ```

    [![コマンドの画像。](images/analyzer-commands.png)](images/analyzer-commands.png#lightbox)

> [!NOTE]
>
> - MDEClientAnalyzer の最新プレビュー バージョンは、次の場所 [https://aka.ms/Betamdeanalyzer](https://aka.ms/Betamdeanalyzer)からダウンロードできます。
>
> - LiveAnalyzer スクリプトは、移行先コンピューターのトラブルシューティング パッケージを次の場所からダウンロードします https://mdatpclientanalyzer.blob.core.windows.net。
>
>   コンピューターが上記の URL に到達することを許可できない場合は、LiveAnalyzer スクリプトを実行する前に、MDEClientAnalyzerPreview.zip ファイルをライブラリにアップロードします。
>
>   ```console
>   PutFile MDEClientAnalyzerPreview.zip -overwrite
>   Run MDELiveAnalyzer.ps1
>   GetFile "C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Downloads\MDEClientAnalyzerResult.zip"
>   ```
>
> - コンピューターがMicrosoft Defender for Endpointクラウド サービスと通信していない場合や、Microsoft Defender for Endpoint ポータルに期待どおりに表示されない場合に備えて、コンピューター上でローカルにデータを収集する方法の詳細については、「[クライアントの接続を確認する」を参照してください。サービス URL をMicrosoft Defender for Endpoint](configure-proxy-internet.md#verify-client-connectivity-to-microsoft-defender-for-endpoint-service-urls)します。
> 
> - [ライブ応答コマンドの例](live-response-command-examples.md)で説明されているように、コマンドの最後にある '&' 記号を使用して、バックグラウンド アクションとしてログを収集することができます。
>   ```console
>   Run MDELiveAnalyzer.ps1&
>   ```


## <a name="see-also"></a>関連項目
- [クライアント アナライザーの概要](overview-client-analyzer.md)
- [クライアント アナライザーのダウンロードと実行](download-client-analyzer.md)
- [Windows でのクライアント アナライザーの実行](run-analyzer-windows.md)
- [macOS または Linux でのクライアント アナライザーの実行](run-analyzer-macos-linux.md)
- [Windows で高度なトラブルシューティングを行うためのデータ収集](data-collection-analyzer.md)
- [アナライザー HTML レポートの理解](analyzer-report.md)
