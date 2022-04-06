---
title: ライブ応答を使用して Microsoft Defender for Endpoint のサポート ログを収集する
description: ライブ応答を使用してログを収集し、Microsoft Defender for Endpoint の問題のトラブルシューティングを行う方法について説明します。
keywords: サポート、ログ、収集、トラブルシューティング、ライブ応答、liveanalyzer、アナライザー、ライブ、応答
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
# <a name="collect-support-logs-in-microsoft-defender-for-endpoint-using-live-response"></a>ライブ応答を使用して Microsoft Defender for Endpoint のサポート ログを収集する


**適用対象:**
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-pullalerts-abovefoldlink)


サポートに連絡する場合は、Microsoft Defender for Endpoint Client Analyzer ツールの出力パッケージを提供する必要があります。

このトピックでは、Live Response を使用してツールを実行する方法について説明します。

1. [Microsoft Defender for Endpoint Client Analyzer](https://aka.ms/BetaMDEAnalyzer) の 'Tools' サブディレクトリから使用可能な必要なスクリプトをダウンロードしてフェッチします。 <br>
たとえば、基本的なセンサーとデバイスの正常性ログを取得するには、.をフェッチします。\Tools\MDELiveAnalyzer.ps1」<br>
Defender ウイルス対策サポート ログも必要な場合 (MpSupportFiles.cab)、.をフェッチします。\Tools\MDELiveAnalyzerAV.ps1" 

2. 調査する [必要があるコンピューターで](live-response.md#initiate-a-live-response-session-on-a-device) ライブ応答セッションを開始します。

3. [ライブラリ **アップロードファイル] を選択します**。

   :::image type="content" source="images/upload-file.png" alt-text="アップロード ファイル" lightbox="images/upload-file.png":::

4. [ファイル **の選択] を選択します**。

   :::image type="content" source="images/choose-file.png" alt-text="[ファイルの選択] ボタン-1" lightbox="images/choose-file.png":::

5. ダウンロードしたファイルを [MDELiveAnalyzer.ps1] を選択し、[確認] を **クリックします。**

   :::image type="content" source="images/analyzer-file.png" alt-text="[ファイルの選択] ボタン-2" lightbox="images/analyzer-file.png":::

6. LiveResponse セッション中は、次のコマンドを使用してアナライザーを実行し、結果ファイルを収集します。

    ```console
    Run MDELiveAnalyzer.ps1
    GetFile "C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Downloads\MDEClientAnalyzerResult.zip"
    ```

    [![コマンドのイメージ。](images/analyzer-commands.png)](images/analyzer-commands.png#lightbox)

> [!NOTE]
>
> - MDEClientAnalyzer の最新のプレビュー バージョンは、次の場所からダウンロードできます。 [https://aka.ms/Betamdeanalyzer](https://aka.ms/Betamdeanalyzer)
>
> - LiveAnalyzer スクリプトは、次のファイルからトラブルシューティング パッケージをダウンロードします https://mdatpclientanalyzer.blob.core.windows.net。
>
>   コンピューターが上記の URL に到達できない場合は、LiveAnalyzer スクリプトを実行する前にMDEClientAnalyzerPreview.zipファイルをライブラリにアップロードします。
>
>   ```console
>   PutFile MDEClientAnalyzerPreview.zip -overwrite
>   Run MDELiveAnalyzer.ps1
>   GetFile "C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Downloads\MDEClientAnalyzerResult.zip"
>   ```
>
> - コンピューターが Microsoft Defender for Endpoint クラウド サービスと通信していない場合、または Microsoft Defender for Endpoint ポータルに予期した通り表示されない場合に、コンピューターでローカルにデータを収集する方法の詳細については、「 [Verify client connectivity to Microsoft Defender for Endpoint service URL](configure-proxy-internet.md#verify-client-connectivity-to-microsoft-defender-for-endpoint-service-urls)」を参照してください。
> 
> - Live response [command の例](live-response-command-examples.md)で説明したように、コマンドの最後に '&' 記号を使用して、ログをバックグラウンド アクションとして収集できます。
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
