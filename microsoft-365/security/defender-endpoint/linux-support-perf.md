---
title: Microsoft Defender for Endpoint on Linux のパフォーマンスの問題のトラブルシューティング
description: Microsoft Defender for Endpoint on Linux のパフォーマンスの問題をトラブルシューティングします。
keywords: microsoft、 defender、 Microsoft Defender for Endpoint, linux, performance
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 6f7a3404ec0ae64e3dcdc4d6a3072e7fc2936646
ms.sourcegitcommit: 6f3bc00a5cf25c48c61eb3835ac069e9f41dc4db
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/24/2022
ms.locfileid: "62172453"
---
# <a name="troubleshoot-performance-issues-for-microsoft-defender-for-endpoint-on-linux"></a>Microsoft Defender for Endpoint on Linux のパフォーマンスの問題のトラブルシューティング

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-investigateip-abovefoldlink)

このドキュメントでは、利用可能な診断ツールを使用して、Linux 上の Defender for Endpoint に関連するパフォーマンスの問題を絞り込み、既存のリソース不足やシステムをそのような状況にしているプロセスを理解して軽減する方法について説明します。 パフォーマンスの問題は、主に、システム上のリソース使用率のプロファイルに応じて、1 つ以上のハードウェア サブシステムのボトルネックによって発生します。 場合によっては、アプリケーションはディスク I/O リソースに敏感であり、CPU 容量が必要な場合や、一部の構成ではサステナブルではなく、新しいプロセスが多すぎるとトリガーされ、ファイル記述子が多すぎます。

実行中のアプリケーションとデバイスの特性によっては、Defender for Endpoint on Linux を実行するときに最適でないパフォーマンスが発生する場合があります。 特に、CPU、ディスク、メモリなどの多くのリソースに短時間でアクセスするアプリケーションまたはシステム プロセスは、Defender for Endpoint on Linux のパフォーマンスの問題につながる可能性があります。

> [!WARNING]
> 開始する前に、 **他のセキュリティ製品がデバイスで現在実行されていないか確認してください**。 複数のセキュリティ製品が競合し、ホストのパフォーマンスに影響を与える可能性があります。

## <a name="troubleshoot-performance-issues-using-real-time-protection-statistics"></a>リアルタイム保護統計を使用したパフォーマンスの問題のトラブルシューティング

**適用対象:**
- AV に関連するパフォーマンスの問題のみ

リアルタイム保護 (RTP) は、デバイスを継続的に監視し、脅威から保護する、Linux 上の Defender for Endpoint の機能です。 ファイルとプロセスの監視、その他のヒューリスティックで構成されます。

次の手順を使用して、これらの問題のトラブルシューティングと軽減を行います。

1. 次のいずれかの方法を使用してリアルタイム保護を無効にし、パフォーマンスが向上するかどうかを確認します。 この方法は、Defender for Endpoint on Linux がパフォーマンスの問題に貢献するかどうかを絞り込むのに役立ちます。

    デバイスが組織によって管理されていない場合は、コマンド ラインからリアルタイム保護を無効にすることができます。

    ```bash
    mdatp config real-time-protection --value disabled
    ```

    ```Output
    Configuration property updated
    ```

    デバイスが組織によって管理されている場合は、「Defender for Endpoint on Linux の設定」の手順に従って、管理者がリアルタイム保護 [を無効にすることができます](linux-preferences.md)。

    > [!NOTE]
    > リアルタイム保護がオフの間にパフォーマンスの問題が解決しない場合、問題の発生源はエンドポイント検出および応答 (EDR) コンポーネントである可能性があります。 この場合は、この記事の **「Microsoft Defender for Endpoint Client Analyzer** を使用したパフォーマンスの問題のトラブルシューティング」セクションの手順に従ってください。

2. 最も多くのスキャンをトリガーしているアプリケーションを見つけるには、Defender for Endpoint on Linux によって収集されたリアルタイム統計を使用できます。

    > [!NOTE]
    > この機能は、バージョン 100.90.70 以降で使用できます。

    この機能は、既定で and チャネル `Dogfood` で有効 `InsiderFast` になっています。 別の更新チャネルを使用している場合は、コマンド ラインからこの機能を有効にできます。

    ```bash
    mdatp config real-time-protection-statistics --value enabled
    ```

    この機能では、リアルタイム保護を有効にする必要があります。 リアルタイム保護の状態を確認するには、次のコマンドを実行します。

    ```bash
    mdatp health --field real_time_protection_enabled
    ```

    エントリが `real_time_protection_enabled` . `true` それ以外の場合は、次のコマンドを実行して有効にしてください。

    ```bash
    mdatp config real-time-protection --value enabled
    ```

    ```Output
    Configuration property updated
    ```

    現在の統計情報を収集するには、次のコマンドを実行します。

    ```bash
    mdatp diagnostic real-time-protection-statistics --output json > real_time_protection.json
    ```

    > [!NOTE]
    > 使用 ```--output json``` (ダブル ダッシュに注意してください) を使用すると、出力形式が解析の準備ができていることを確認します。

    このコマンドの出力には、すべてのプロセスと関連するスキャン アクティビティが表示されます。

3. Linux システムで、次のコマンドを使用して **python パーサー high_cpu_parser.py の** サンプルをダウンロードします。

    ```bash
    wget -c https://raw.githubusercontent.com/microsoft/mdatp-xplat/master/linux/diagnostic/high_cpu_parser.py
    ```

    このコマンドの出力は、次のようになります。


    ```Output
    --2020-11-14 11:27:27-- https://raw.githubusercontent.com/microsoft.mdatp-xplat/master/linus/diagnostic/high_cpu_parser.py
    Resolving raw.githubusercontent.com (raw.githubusercontent.com)... 151.101.xxx.xxx
    Connecting to raw.githubusercontent.com (raw.githubusercontent.com)| 151.101.xxx.xxx| :443... connected.
    HTTP request sent, awaiting response... 200 OK
    Length: 1020 [text/plain]
    Saving to: 'high_cpu_parser.py'
    100%[===========================================>] 1,020    --.-K/s   in 0s
    ```

4. 次に、次のコマンドを入力します。

    ```bash
    chmod +x high_cpu_parser.py
    ```

    ```bash
    cat real_time_protection.json | python high_cpu_parser.py  > real_time_protection.log
    ```

      上記の出力は、パフォーマンスの問題に対する上位の投稿者の一覧です。 最初の列はプロセス識別子 (PID)、2 番目の列はプロセス名、最後の列はスキャンされたファイルの数であり、影響によって並べ替えます。
    たとえば、コマンドの出力は次のようになります。 

    ```Output
    ... > python ~/repo/mdatp-xplat/linux/diagnostic/high_cpu_parser.py <~Downloads/output.json | head -n 10
    27432 None 76703
    73467 actool     1249
    73914 xcodebuild 1081
    73873 bash 1050
    27475 None 836
    1    launchd    407
    73468 ibtool     344
    549  telemetryd_v1   325
    4764 None 228
    125  CrashPlanService 164
    ```

    Defender for Endpoint on Linux のパフォーマンスを向上するには、行の下に数値が最も多いディフェンダーを見つけて除外 `Total files scanned` を追加します。 詳細については、「Linux での Defender for Endpoint の除外の構成と [検証」を参照してください](linux-exclusions.md)。

    > [!NOTE]
    > アプリケーションは、統計をメモリに格納し、ファイルのアクティビティが開始され、リアルタイム保護が有効にされた後にのみ追跡します。 リアルタイム保護がオフの前または期間中に起動されたプロセスはカウントされません。 さらに、トリガーされたスキャンがカウントされるイベントのみ。

5. パフォーマンスの問題に寄与するプロセスまたはディスクの場所を除外して、Microsoft Defender for Endpoint on Linux を構成し、リアルタイム保護を再び有効にしてください。

    詳細については、「[Linux 用の Microsoft Defender for Endpoint の除外を構成および検証する](linux-exclusions.md)」 を参照してください。

## <a name="troubleshoot-performance-issues-using-microsoft-defender-for-endpoint-client-analyzer"></a>Microsoft Defender for Endpoint Client Analyzer を使用したパフォーマンスの問題のトラブルシューティング

**適用対象:**
- AV やエンドポイントなどのすべての使用可能な Defender for Endpoint コンポーネントのパフォーマンスEDR  

Microsoft Defender for Endpoint Client Analyzer (MDECA) は、Linux 上のオンボード デバイスのパフォーマンスの問題をトラブルシューティングするために、トレース、ログ、および診断 [情報を収集](/microsoft-365/security/defender-endpoint/onboard-configure) できます。

> [!NOTE]
> Microsoft Defender for Endpoint Client Analyzer ツールは、Microsoft Defender for Endpoint で発生する可能性のある問題のトラブルシューティングに役立つ IP アドレス、PC 名などの情報を収集するために、Microsoft カスタマー サポート サービス (CSS) によって定期的に使用されます。 プライバシーに関する声明の詳細については [、「Microsoft Privacy Statement」を参照してください](https://privacy.microsoft.com/privacystatement)。

### <a name="requirements"></a>要件

- クライアント アナライザーは、Microsoft Defender for Endpoint[](microsoft-defender-endpoint-linux.md#system-requirements)へのオンボーディングの前または後に、サポートされている Linux ディストリビューションで実行できます。
- ダウンロード可能な最新のプレビュー エディションから Linux 用のクライアント アナライザーをダウンロードするには、こちらをクリックしてください。 <https://aka.ms/XMDEClientAnalyzer>
- デバイスがプロキシの背後にある場合は、プロキシ サーバーを環境変数として mde_support_tool.sh スクリプトに渡す必要があります。 例: `https_proxy=https://myproxy.contoso.com:8080 ./mde_support_tool.sh"`

### <a name="run-the-client-analyzer-on-linux"></a>Linux でクライアント アナライザーを実行する

ターミナルまたは SSH を関連するコンピューターに開き、次のコマンドを実行します。

1. `wget --quiet -O XMDEClientAnalyzer.zip https://aka.ms/XMDEClientAnalyzer`
2. `unzip -q XMDEClientAnalyzer.zip`
3. `cd XMDEClientAnalyzer`
4. `chmod +x mde_support_tool.sh`
5. ルート以外の使用として実行して、必要なピップと lxml をインストールします。 `./mde_support_tool.sh`
6. 実際の診断パッケージを収集し、結果アーカイブ ファイルを生成するには、ルートとして再度実行します。例 `./mde_support_tool.sh -d` :

   ![コマンド ラインの例のイメージ。](images/4ca188f6c457e335abe3c9ad3eddda26.png)

> [!NOTE]
> - 結果の出力を生成するには、アナライザーに 'lxml' が必要です。 インストールされていない場合、アナライザーは以下の Python パッケージの公式リポジトリから取得します。 <https://files.pythonhosted.org/packages/\*/lxml\*.whl>
> 
> - また、現在、ツールのインストールには Python バージョン 3 以降が必要です。
>
> - Python 3 を使用できないマシンまたは lxml コンポーネントをフェッチできないコンピューターで実行している場合は、要件を満たしていないバイナリ ベースのバージョンのアナライザー [(XMDE Client Analyzer Binary)](https://aka.ms/XMDEClientAnalyzerBinary)をダウンロードできます。

### <a name="additional-syntax-help"></a>その他の構文ヘルプ:

**-h** \# ヘルプ<br>
\# ヘルプ メッセージを表示する

**パフォーマンス** \# パフォーマンス<br>
\# オンデマンドで再現できるパフォーマンスの問題を分析するために、広範なトレースを収集します。 ベンチマーク `--length=<seconds>` の期間を指定する場合に使用します。

**-o** \# 出力<br>
\# 結果ファイルの宛先パスを指定する

**-nz** \# No-Zip<br>
\# 設定すると、結果のアーカイブ ファイルの代わりにディレクトリが作成されます

**-f** \# Force<br>
\# 出力が宛先パスに既に存在する場合は上書きする

### <a name="result-package-contents"></a>結果パッケージの内容

- report.html

  説明: アナライザー スクリプトがコンピューターで実行できる結果とガイダンスを含むメインの HTML 出力ファイル。

- mde_diagnostic.zip

  説明: Linux で mdatp 診断作成を実行 *するときに生成される診断出力* と同 [じ](/windows/security/threat-protection/microsoft-defender-atp/linux-resources#collect-diagnostic-information)

- mde.xml

  説明: 実行中に生成され、HTML レポート ファイルのビルドに使用される XML 出力。

- Processes_information.txt

  説明: システムで実行中の Microsoft Defender for Endpoint 関連プロセスの詳細が含まれる。

- Log.txt

  説明: データ収集中に画面に書き込まれた同じログ メッセージが含まれます。

- Health.txt

  説明: mdatp health コマンドを実行するときに表示されるのと同じ基本的 *な正常性出力* 。

- Events.xml

  説明: HTML レポートの作成時にアナライザーによって使用される追加の XML ファイル。

- Auditd_info.txt

  説明: Linux OS の監査されたサービスと関連コンポーネント [の](/windows/security/threat-protection/microsoft-defender-atp/linux-support-events) 詳細

- perf_benchmark.tar.gz

  説明: パフォーマンス テストレポート。 これは、performance パラメーターを使用している場合にのみ表示されます。

> [!NOTE]
> 上記の手順に従った後もパフォーマンスの問題が解決しない場合は、カスタマー サポートに問い合わせ、詳細な手順と軽減策を確認してください。



## <a name="see-also"></a>関連項目

- [エージェントの正常性に関する問題の調査](health-status.md)
