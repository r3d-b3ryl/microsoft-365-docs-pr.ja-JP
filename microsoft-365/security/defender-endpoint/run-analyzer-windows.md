---
title: Windows でクライアント アナライザーを実行する
description: Windows でMicrosoft Defender for Endpointクライアント アナライザーを実行する方法について説明します。
keywords: クライアント アナライザー, センサーのトラブルシューティング, アナライザー, mdeanalyzer, windows
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
ms.openlocfilehash: 51eaa6ddcaf50a48ccbd8ffc000a79049c1d9842
ms.sourcegitcommit: d1b60ed9a11f5e6e35fbaf30ecaeb9dfd6dd197d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/29/2022
ms.locfileid: "66489472"
---
# <a name="run-the-client-analyzer-on-windows"></a>Windows でクライアント アナライザーを実行する

**適用対象:**
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

1. 調査する必要がある Windows コンピューターに [MDE クライアント アナライザー ツール](https://aka.ms/mdatpanalyzer) をダウンロードします。

2. コンピューター上のMDEClientAnalyzer.zipの内容を抽出します。

3. 管理者特権でコマンド プロンプトを開きます。
    1. **[スタート]** をクリックし、「**cmd**」と入力します。
    2. **[コマンド プロンプト]** を右クリックして **[管理者として実行]** を選択します。

4. 次のコマンドを入力して、**Enter** キーを押します。

   ```dos
   HardDrivePath\MDEClientAnalyzer.cmd
   ```

   **次のように、HardDrivePath をツールの抽出先のパスに置き換えます。**

   ```dos
   C:\Work\tools\MDEClientAnalyzer\MDEClientAnalyzer.cmd
   ```

上記に加えて、 [ライブ応答を使用してアナライザー サポート ログを収集](troubleshoot-collect-support-log.md)するオプションもあります。

> [!NOTE]
> Windows 10/11、Windows Server 2019/2022、または[最新の統合ソリューション](configure-server-endpoints.md#new-windows-server-2012-r2-and-2016-functionality-in-the-modern-unified-solution)がインストールされた Windows Server 2012R2/2016 では、クライアント アナライザー スクリプトが実行可能ファイルを呼び出して、`MDEClientAnalyzer.exe`クラウド サービス URL への接続テストを実行します。
>
> Windows 8.1、Windows Server 2016、または Microsoft Monitoring Agent (MMA) がオンボードに使用されている以前の OS エディションでは、クライアント アナライザー スクリプトは実行可能ファイルを呼び出`MDEClientAnalyzerPreviousVersion.exe`し、コマンドおよびコントロール (CnC) URL の接続テストを実行すると同時に、サイバー データ チャネル URL 用の Microsoft Monitoring Agent 接続ツール`TestCloudConnection.exe`も呼び出します。


アナライザーに含まれるすべての PowerShell スクリプトとモジュールは、Microsoft によって署名されています。
ファイルが何らかの方法で変更された場合、アナライザーは次のエラーで終了する必要があります。

:::image type="content" source="images/sigerror.png" alt-text="クライアント アナライザー エラー" lightbox="images/sigerror.png":::


このエラーが表示された場合、issuerInfo.txt出力には、それが発生した理由と影響を受けたファイルに関する詳細情報が含まれます。

:::image type="content" source="images/issuerinfo.png" alt-text="発行者の情報" lightbox="images/issuerinfo.png":::


MDEClientAnalyzer.ps1が変更された後の内容の例:

:::image type="content" source="images/modified-ps1.png" alt-text="変更された ps1 ファイル" lightbox="images/modified-ps1.png":::



## <a name="result-package-contents-on-windows"></a>Windows 上の結果パッケージの内容

> [!NOTE]
> キャプチャされる正確なファイルは、次のような要因によって変わる場合があります。
>
> - アナライザーを実行するウィンドウのバージョン。
> - コンピューターでのイベント ログ チャネルの可用性。
> - EDR センサーの開始状態 (マシンがまだオンボードされていない場合はセンスが停止します)。
> - アナライザー コマンドで高度なトラブルシューティング パラメーターが使用された場合。

既定では、アンパックされたMDEClientAnalyzerResult.zip ファイルには次の項目が含まれます。

- MDEClientAnalyzer.htm

  これはメインの HTML 出力ファイルです。このファイルには、コンピューターで実行されるアナライザー スクリプトが生成できる結果とガイダンスが含まれます。

- SystemInfoLogs \[フォルダー\]
  - AddRemovePrograms.csv

    説明: レジストリから収集された x64 OS にインストールされている x64 ソフトウェアの一覧。

  - AddRemoveProgramsWOW64.csv

    説明: レジストリから収集された x64 OS にインストールされている x86 ソフトウェアの一覧。

    - CertValidate.log

      説明: [CertUtil](/windows-server/administration/windows-commands/certutil) を呼び出すことによって実行された証明書失効の詳細な結果。

    - dsregcmd.txt

      説明: [dsregcmd](/azure/active-directory/devices/troubleshoot-device-dsregcmd) の実行からの出力。 これにより、マシンの Azure AD の状態に関する詳細が表示されます。

    - IFEO.txt

      説明: コンピューターで構成された [イメージ ファイル実行オプション](/previous-versions/windows/desktop/xperf/image-file-execution-options) の出力

    - MDEClientAnalyzer.txt

      説明: これは、アナライザー スクリプトの実行の詳細を示す詳細テキスト ファイルです。

    - MDEClientAnalyzer.xml

      説明: アナライザー スクリプトの結果を含む XML 形式。

    - RegOnboardedInfoCurrent.Json

      説明: レジストリから JSON 形式で収集されたオンボードコンピューター情報。

  - RegOnboardingInfoPolicy.Json

    説明: オンボード ポリシー構成は、レジストリから JSON 形式で収集されます。

    - SCHANNEL.txt

      説明: レジストリから収集されたコンピューターに適用される [SCHANNEL 構成](/windows-server/security/tls/manage-tls) の詳細。

    - SessionManager.txt

      説明: Session Manager 固有の設定がレジストリから収集されます。

    - SSL_00010002.txt

      説明: レジストリから収集されたマシンに適用される [SSL 構成](/windows-server/security/tls/manage-tls) の詳細。

- EventLogs [フォルダー]

  - utc.evtx

    説明: DiagTrack イベント ログのエクスポート

  - senseIR.evtx

    説明: 自動調査イベント ログのエクスポート

  - sense.evtx

    説明: Sensor メイン イベント ログのエクスポート

  - OperationsManager.evtx

    説明: Microsoft Monitoring Agent イベント ログのエクスポート




## <a name="see-also"></a>関連項目

- [クライアント アナライザーの概要](overview-client-analyzer.md)
- [クライアント アナライザーのダウンロードと実行](download-client-analyzer.md)
- [Windows で高度なトラブルシューティングを行うためのデータ収集](data-collection-analyzer.md)
- [アナライザー HTML レポートの理解](analyzer-report.md)
