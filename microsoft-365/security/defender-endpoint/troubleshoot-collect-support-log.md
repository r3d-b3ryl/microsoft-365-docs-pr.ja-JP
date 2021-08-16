---
title: ライブ応答を使用して Microsoft Defender for Endpoints のサポート ログを収集する
description: ライブ応答を使用してログを収集し、Microsoft Defender for Endpoints の問題のトラブルシューティングを行う方法について説明します。
keywords: サポート、ログ、収集、トラブルシューティング、ライブ応答、liveanalyzer、アナライザー、ライブ、応答
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
ms.openlocfilehash: 518194e3cbf185da415104991e1d7186f5912953
ms.sourcegitcommit: a0185d6b0dd091db6e1e1bfae2f68ab0e3cf05e5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/13/2021
ms.locfileid: "58250571"
---
# <a name="collect-support-logs-in-microsoft-defender-for-endpoint-using-live-response"></a>ライブ応答を使用して Microsoft Defender for Endpoint のサポート ログを収集する


**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Defender for Endpoint を体験してみませんか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-pullalerts-abovefoldlink)


サポートに連絡する場合は、Microsoft Defender for Endpoint Client Analyzer ツールの出力パッケージを提供する必要があります。

このトピックでは、Live Response を使用してツールを実行する方法について説明します。

1. 適切なスクリプトをダウンロードする
   - Microsoft Defender for Endpoint クライアント センサー ログのみ:LiveAnalyzer.ps1 [ スクリプト](https://aka.ms/MDELiveAnalyzer)です。
      - 結果パッケージの概算サイズ: ~100Kb
   - Microsoft Defender for Endpoint クライアント センサーとウイルス対策ログ: [LiveAnalyzer+MDAV.ps1 スクリプト](https://aka.ms/MDELiveAnalyzerAV)です。
       - 結果パッケージの概算サイズ: ~10 Mb

2. 調査する [必要があるコンピューターで](live-response.md#initiate-a-live-response-session-on-a-device) ライブ応答セッションを開始します。

3. [ライブラリ **アップロードファイルを選択します**。

    ![アップロード ファイルのイメージ](images/upload-file.png)

4. [ファイル **の選択] を選択します**。

    ![ファイルの選択ボタン 1 のイメージ](images/choose-file.png)

5. [ファイル] という名前のダウンロードしたMDELiveAnalyzer.ps1を選択し、[確認] を **クリックします。**

   ![ファイルの選択ボタン 2 のイメージ](images/analyzer-file.png)

6. LiveResponse セッション中は、次のコマンドを使用してアナライザーを実行し、結果ファイルを収集します。

    ```console
    Run MDELiveAnalyzer.ps1
    GetFile "C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Downloads\MDEClientAnalyzerResult.zip"
    ```

    [![コマンドのイメージ](images/analyzer-commands.png)](images/analyzer-commands.png#lightbox)

> [!NOTE]
>
> - MDEClientAnalyzer の最新のプレビュー バージョンは、次の場所からダウンロードできます [https://aka.ms/Betamdeanalyzer](https://aka.ms/Betamdeanalyzer) 。
>
> - LiveAnalyzer スクリプトは、次のファイルからトラブルシューティング パッケージをダウンロードします https://mdatpclientanalyzer.blob.core.windows.net 。
>
>   コンピューターが上記の URL に到達できない場合は、LiveAnalyzer スクリプトを実行する前にMDEClientAnalyzerPreview.zipファイルをライブラリにアップロードします。
>
>   ```console
>   PutFile MDEClientAnalyzerPreview.zip -overwrite
>   Run MDELiveAnalyzer.ps1
>   GetFile "C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Downloads\MDEClientAnalyzerResult.zip"
>   ```
>
> - コンピューターが Microsoft Defender for Endpoint クラウド サービスと通信していない場合、または Microsoft Defender for Endpoint ポータルに予期した通り表示されない場合に、コンピューターでローカルにデータを収集する方法の詳細については、「Verify client [connectivity to Microsoft Defender for Endpoint](configure-proxy-internet.md#verify-client-connectivity-to-microsoft-defender-for-endpoint-service-urls)service URL」を参照してください。


## <a name="see-also"></a>関連項目
- [クライアント アナライザーの概要](overview-client-analyzer.md)
- [クライアント アナライザーをダウンロードして実行する](download-client-analyzer.md)
- [クライアント アナライザーをコンピューターで実行Windows](run-analyzer-windows.md)
- [macOS または Linux でクライアント アナライザーを実行する](run-analyzer-macos-linux.md)
- [詳細なトラブルシューティングを行うデータのWindows](data-collection-analyzer.md)
- [アナライザー HTML レポートについて](analyzer-report.md)

