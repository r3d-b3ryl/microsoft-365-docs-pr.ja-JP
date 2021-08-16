---
title: クライアント アナライザーをコンピューターで実行Windows
description: Microsoft Defender for Endpoint Client Analyzer を実行する方法については、Windows。
keywords: クライアント アナライザー、センサー、アナライザー、mdeanalyzer、Windows のトラブルシューティング
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 754ec7b6cdd6e6c5e3c9f5765d839bd94a1d720b
ms.sourcegitcommit: a0185d6b0dd091db6e1e1bfae2f68ab0e3cf05e5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/13/2021
ms.locfileid: "58254897"
---
#  <a name="run-the-client-analyzer-on-windows"></a>クライアント アナライザーをコンピューターで実行Windows

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2146631)


1.  [MDE クライアント アナライザー ツールを、](https://aka.ms/mdatpanalyzer)調査Windowsコンピューターにダウンロードします。

2.  コンピューター上のMDEClientAnalyzer.zipを抽出します。

3.  管理者特権でコマンド プロンプトを開きます。
    1. **[スタート]** をクリックし、「**cmd**」と入力します。
    2. **[コマンド プロンプト]** を右クリックして **[管理者として実行]** を選択します。

4.  次のコマンドを入力して、**Enter** キーを押します。

```
HardDrivePath\MDEClientAnalyzer.cmd
```

**HardDrivePath を、ツールが抽出されたパスに置き換える例を次に示します。**

`C:\Work\tools\MDATPClientAnalyzer\MDEClientAnalyzer.cmd`

上記に加えて、ライブ応答を使用してアナライザー サポート ログ[を収集するオプションも用意されています。](troubleshoot-collect-support-log.md)

> [!NOTE]  
> Windows 10、Windows Server 2019 以降の OS エディションでは、クライアント アナライザー スクリプトは、クラウド サービス URL への接続テストを実行するために呼び出される実行可能ファイルを呼び出します。 `MDEClientAnalyzer.exe` <br> <br> Windows 8.1、Windows Server 2016、または以前の OS エディションでは、クライアント アナライザー スクリプトは、コマンドとコントロール (CnC) URL の接続テストを実行するために呼び出される実行可能ファイルを呼び出し、サイバー データ チャネル URL の Microsoft Monitoring Agent 接続ツールにも呼び出します。 `MDEClientAnalyzerPreviousVersion.exe` `TestCloudConnection.exe`

## <a name="result-package-contents-on-windows"></a>結果パッケージの内容がWindows

> [!NOTE]    
> キャプチャされる正確なファイルは、次のような要因によって変わる場合があります。
> -   アナライザーが実行されるウィンドウのバージョン。
> -   コンピューター上のイベント ログ チャネルの可用性。
> -   センサーの開始状態 (EDRまだオンボードされていない場合、センサーは停止します)。
>-   アナライザー コマンドで高度なトラブルシューティング パラメーターが使用されている場合。

既定では、開梱されたMDEClientAnalyzerResult.zipには、次の項目が含まれます。

-   MDEClientAnalyzer.htmこれはメインの HTML 出力ファイルであり、コンピューター上でアナライザー スクリプトが実行できる結果とガイダンス \| が含まれる。

-   SystemInfoLogs [フォルダー]

    -   AddRemovePrograms.csv <br> 説明: レジストリから収集されたインストール済みソフトウェアの一覧。

-   AddRemoveProgramsWOW64.csv <br> 説明: レジストリから収集された x64 OS ソフトウェアにインストールされている x86 ソフトウェアの一覧。

    -   CertValidate.log <br> 説明: [CertUtil](/windows-server/administration/windows-commands/certutil)を呼び出して実行される証明書失効の詳細な結果です。

    -   dsregcmd.txt <br> 説明: [dsregcmd の実行からの出力](/azure/active-directory/devices/troubleshoot-device-dsregcmd)。
        これにより、コンピューターの Azure AD状態に関する詳細が表示されます。

    -   IFEO.txt <br> 説明: コンピューターで [構成されているイメージ ファイル実行オプション](/previous-versions/windows/desktop/xperf/image-file-execution-options) の出力

    -   MDEClientAnalyzer.txt <br> 説明: アナライザー スクリプトの実行の詳細を示す詳細なテキスト ファイルです。

    -   MDEClientAnalyzer.xml <br> 説明: アナライザー スクリプトの結果を含む XML 形式。

    -   RegOnboardedInfoCurrent.Jsオン <br> 説明: レジストリから JSON 形式で収集されたオンボード コンピューター情報。

    -   RegOnboardingInfoPolicy.Jsオン <br> 説明: レジストリから JSON 形式で収集されたオンボーディング ポリシー構成。

    -   SCHANNEL.txt <br> 説明: レジストリから [収集されたコンピューター](/windows-server/security/tls/manage-tls) に適用される SCHANNEL 構成の詳細。

    -   SessionManager.txt <br> 説明: セッション マネージャー固有の設定はレジストリから収集されます。

    -   SSL_00010002.txt <br> 説明: レジストリから [収集された](/windows-server/security/tls/manage-tls) コンピューターに適用される SSL 構成の詳細。

-   EventLogs [フォルダー]

    -   utc.evtx <br> 説明: DiagTrack イベント ログのエクスポート

    -   senseIR.evtx <br> 説明: 自動調査イベント ログのエクスポート

    -   sense.evtx <br> 説明: Sensor メイン イベント ログのエクスポート

    -   OperationsManager.evtx <br> 説明: イベント ログMicrosoft Monitoring Agentエクスポートする


## <a name="see-also"></a>関連項目
- [クライアント アナライザーの概要](overview-client-analyzer.md)
- [クライアント アナライザーをダウンロードして実行する](download-client-analyzer.md)
- [詳細なトラブルシューティングを行うデータのWindows](data-collection-analyzer.md)
- [アナライザー HTML レポートについて](analyzer-report.md)
