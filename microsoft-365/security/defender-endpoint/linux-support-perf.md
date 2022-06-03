---
title: Linux でのMicrosoft Defender for Endpointのパフォーマンスの問題のトラブルシューティング
description: Linux 上のMicrosoft Defender for Endpointのパフォーマンスの問題のトラブルシューティングを行います。
keywords: microsoft、defender、Microsoft Defender for Endpoint、Linux、パフォーマンス
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
- m365-initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 3452f36068facc92885047184f7e00828f569cbc
ms.sourcegitcommit: 35f167725bec5fd4fe131781a53d96b060cf232d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/03/2022
ms.locfileid: "65873008"
---
# <a name="troubleshoot-performance-issues-for-microsoft-defender-for-endpoint-on-linux"></a>Linux でのMicrosoft Defender for Endpointのパフォーマンスの問題のトラブルシューティング

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-investigateip-abovefoldlink)

このドキュメントでは、使用可能な診断ツールを使用して Defender for Endpoint on Linux に関連するパフォーマンスの問題を絞り込み、既存のリソース不足やシステムをそのような状況に陥れているプロセスを理解して軽減する方法について説明します。 パフォーマンスの問題は、主に、システム上のリソース使用率のプロファイルに応じて、1 つ以上のハードウェア サブシステムのボトルネックによって発生します。 アプリケーションはディスク I/O リソースに対して機密性が高く、より多くの CPU 容量が必要な場合があります。また、一部の構成は持続可能ではなく、新しいプロセスのトリガーが多すぎて、ファイル記述子が多すぎる場合があります。

実行中のアプリケーションとデバイスの特性によっては、Linux 上で Defender for Endpoint を実行するときに最適でないパフォーマンスが発生する場合があります。 特に、CPU、ディスク、メモリなどの多くのリソースに短時間でアクセスするアプリケーションやシステム プロセスは、Defender for Endpoint on Linux のパフォーマンスの問題につながる可能性があります。

> [!WARNING]
> 開始する前に、 **デバイスで他のセキュリティ製品が現在実行されていないことを確認してください**。 複数のセキュリティ製品が競合し、ホストのパフォーマンスに影響を与える可能性があります。

## <a name="troubleshoot-performance-issues-using-real-time-protection-statistics"></a>リアルタイム保護統計を使用したパフォーマンスの問題のトラブルシューティング

**適用対象:**
- AV に関連するパフォーマンスの問題のみ

リアルタイム保護 (RTP) は、脅威からデバイスを継続的に監視および保護する、Linux 上の Defender for Endpoint の機能です。 ファイルとプロセスの監視とその他のヒューリスティックで構成されます。

これらの問題のトラブルシューティングと軽減には、次の手順を使用できます。

1. 次のいずれかの方法を使用してリアルタイム保護を無効にし、パフォーマンスが向上するかどうかを確認します。 このアプローチは、Defender for Endpoint on Linux がパフォーマンスの問題に貢献しているかどうかを絞り込むのに役立ちます。

    デバイスが組織によって管理されていない場合は、コマンド ラインからリアルタイム保護を無効にすることができます。

    ```bash
    mdatp config real-time-protection --value disabled
    ```

    ```Output
    Configuration property updated
    ```

    デバイスが組織によって管理されている場合は、「 [Defender for Endpoint on Linux の基本設定を設定](linux-preferences.md)する」の手順を使用して、管理者がリアルタイム保護を無効にすることができます。

    > [!NOTE]
    > リアルタイム保護がオフの間もパフォーマンスの問題が解決しない場合、問題の原因はエンドポイントでの検出と対応 (EDR) コンポーネントである可能性があります。 この場合は、この記事の「**Microsoft Defender for Endpoint Client Analyzer を使用したパフォーマンスの問題のトラブルシューティング**」セクションの手順に従ってください。

2. 最もスキャンをトリガーしているアプリケーションを見つけるには、Defender for Endpoint on Linux によって収集されたリアルタイム統計を使用できます。

    > [!NOTE]
    > この機能は、バージョン 100.90.70 以降で使用できます。

    この機能は、チャネルと`InsiderFast`チャネルで既定で`Dogfood`有効になっています。 別の更新チャネルを使用している場合は、コマンド ラインからこの機能を有効にすることができます。

    ```bash
    mdatp config real-time-protection-statistics --value enabled
    ```

    この機能を有効にするには、リアルタイムの保護が必要です。 リアルタイム保護の状態を確認するには、次のコマンドを実行します。

    ```bash
    mdatp health --field real_time_protection_enabled
    ```

    エントリ`true`が `real_time_protection_enabled` . それ以外の場合は、次のコマンドを実行して有効にします。

    ```bash
    mdatp config real-time-protection --value enabled
    ```

    ```Output
    Configuration property updated
    ```

    現在の統計を収集するには、次のコマンドを実行します。

    ```bash
    mdatp diagnostic real-time-protection-statistics --output json > real_time_protection.json
    ```

    > [!NOTE]
    > (二重ダッシュに注意して) を使用すると ```--output json``` 、出力形式を解析する準備が整います。

    このコマンドの出力には、すべてのプロセスとそれに関連するスキャン アクティビティが表示されます。

3. Linux システムで、次のコマンドを使用してサンプル Python パーサー **high_cpu_parser.py** をダウンロードします。

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

      上記の出力は、パフォーマンスの問題に対する主要な貢献者の一覧です。 最初の列はプロセス識別子 (PID)、2 番目の列はプロセス名、最後の列はスキャンされたファイルの数で、影響によって並べ替えられます。
    たとえば、コマンドの出力は次のようになります。 

    ```Output
    ... > python ~/repo/mdatp-xplat/linux/diagnostic/high_cpu_parser.py <~Downloads/output.json | head -n 10
    27432 None 76703
    73467 actool    1249
    73914 xcodebuild 1081
    73873 bash 1050
    27475 None 836
    1    launchd     407
    73468 ibtool     344
    549  telemetryd_v1   325
    4764 None 228
    125  CrashPlanService 164
    ```

    Linux 上の Defender for Endpoint のパフォーマンスを向上させるには、行の下の数値が最も高いものを `Total files scanned` 見つけて、除外を追加します。 詳細については、「 [Defender for Endpoint on Linux の除外を構成して検証する」を](linux-exclusions.md)参照してください。

    > [!NOTE]
    > アプリケーションは、メモリに統計を格納し、ファイルアクティビティが開始され、リアルタイム保護が有効になっているため、ファイル アクティビティのみを追跡します。 リアルタイム保護がオフになっていた期間の前または期間中に起動されたプロセスはカウントされません。 さらに、トリガーされたスキャンのイベントのみがカウントされます。

5. パフォーマンスの問題に影響するプロセスまたはディスクの場所を除外して Linux でMicrosoft Defender for Endpointを構成し、リアルタイム保護を再度有効にします。

    詳細については、「[Linux 用の Microsoft Defender for Endpoint の除外を構成および検証する](linux-exclusions.md)」 を参照してください。

## <a name="troubleshoot-performance-issues-using-microsoft-defender-for-endpoint-client-analyzer"></a>Microsoft Defender for Endpoint クライアント アナライザーを使用したパフォーマンスの問題のトラブルシューティング

**適用対象:**
- AV やEDRなど、使用可能なすべての Defender for Endpoint コンポーネントのパフォーマンスの問題  

Microsoft Defender for Endpoint Client Analyzer (MDECA) は、Linux [上のオンボード デバイス](/microsoft-365/security/defender-endpoint/onboard-configure)のパフォーマンスの問題をトラブルシューティングするために、トレース、ログ、診断情報を収集できます。

> [!NOTE]
> Microsoft Defender for Endpoint クライアント アナライザー ツールは、Microsoft カスタマー サポート サービス (CSS) によって定期的に使用され、IP アドレス(ただしこれらに限定されません)、Microsoft Defender for Endpointで発生する可能性がある問題のトラブルシューティングに役立つ PC 名などの情報を収集します。 プライバシーに関する声明の詳細については、 [Microsoft のプライバシーに関する声明](https://privacy.microsoft.com/privacystatement)を参照してください。

### <a name="requirements"></a>要件

- クライアント アナライザーは、Microsoft Defender for Endpointにオンボードする前または後に、[サポートされている Linux](microsoft-defender-endpoint-linux.md#system-requirements) ディストリビューションで実行できます。
- Linux 用クライアント アナライザーを、ダウンロードできる最新のプレビュー エディションからダウンロードします。 <https://aka.ms/XMDEClientAnalyzer>
- デバイスがプロキシの背後にある場合は、プロキシ サーバーを環境変数としてmde_support_tool.sh スクリプトに渡すだけです。 例: `https_proxy=https://myproxy.contoso.com:8080 ./mde_support_tool.sh"`

### <a name="run-the-client-analyzer-on-linux"></a>Linux でクライアント アナライザーを実行する

関連するコンピューターにターミナルまたは SSH を開き、次のコマンドを実行します。

1. `wget --quiet -O XMDEClientAnalyzer.zip https://aka.ms/XMDEClientAnalyzer`
2. `unzip -q XMDEClientAnalyzer.zip`
3. `cd XMDEClientAnalyzer`
4. `chmod +x mde_support_tool.sh`
5. 必要な pip コンポーネントと lxml コンポーネントをインストールするために、ルート以外の使用として実行します。 `./mde_support_tool.sh`
6. 実際の診断パッケージを収集し、結果アーカイブ ファイルを生成するには、ルートとして再実行します。 `./mde_support_tool.sh -d`

   ![コマンド ラインの例の画像。](images/4ca188f6c457e335abe3c9ad3eddda26.png)

> [!NOTE]
> - アナライザーでは、結果出力を生成するために 'lxml' が必要です。 インストールされていない場合、アナライザーは、以下の Python パッケージの公式リポジトリからそれをフェッチしようとします。 <https://pypi.org/search/?q=lxml>
> 
> - さらに、このツールでは現在、Python バージョン 3 以降をインストールする必要があります。
>
> - Python 3 を使用できないコンピューターまたは lxml コンポーネントをフェッチできないマシンで実行している場合は、[XMDE クライアント アナライザー バイナリ](https://aka.ms/XMDEClientAnalyzerBinary)という要件を持たないバイナリ ベースのバージョンのアナライザーをダウンロードできます。

### <a name="additional-syntax-help"></a>その他の構文ヘルプ:

**-h** \# ヘルプ<br>
\# ヘルプ メッセージを表示する

**パフォーマンス** \# パフォーマンス<br>
\# オンデマンドで再現できるパフォーマンスの問題を分析するための広範なトレースを収集します。 ベンチマークの期間を指定するために使用 `--length=<seconds>` します。

**-o** \# 出力<br>
\# 結果ファイルの宛先パスを指定する

**-nz** \# No-Zip<br>
\# 設定すると、結果として生成されるアーカイブ ファイルの代わりにディレクトリが作成されます

**-f** \# 力<br>
\# 出力が宛先パスに既に存在する場合は上書きする

### <a name="result-package-contents"></a>結果パッケージの内容

- report.html

  説明: アナライザー スクリプトがコンピューターで実行できる結果とガイダンスを含むメイン HTML 出力ファイル。

- mde_diagnostic.zip

  説明: [Linux](/windows/security/threat-protection/microsoft-defender-atp/linux-resources#collect-diagnostic-information) で *mdatp 診断作成* を実行するときに生成されるのと同じ診断出力

- mde.xml

  説明: 実行中に生成され、HTML レポート ファイルのビルドに使用される XML 出力。

- Processes_information.txt

  説明: システムで実行中のMicrosoft Defender for Endpoint関連プロセスの詳細が含まれます。

- Log.txt

  説明: データ収集中に画面に書き込まれたのと同じログ メッセージが含まれます。

- Health.txt

  説明: *mdatp* health コマンドの実行時に表示されるのと同じ基本的な正常性出力。

- Events.xml

  説明: HTML レポートを作成するときにアナライザーによって使用される追加の XML ファイル。

- Audited_info.txt

  説明: [Linux](/microsoft-365/security/defender-endpoint/linux-resources) OS の監査済みサービスと関連コンポーネントの詳細

- perf_benchmark.tar.gz

  説明: パフォーマンス テスト レポート。 これは、パフォーマンス パラメーターを使用している場合にのみ表示されます。

> [!NOTE]
> 上記の手順に従った後、パフォーマンスの問題が解決しない場合は、詳細な手順と軽減策についてカスタマー サポートにお問い合わせください。



## <a name="see-also"></a>関連項目

- [エージェントの正常性に関する問題の調査](health-status.md)
