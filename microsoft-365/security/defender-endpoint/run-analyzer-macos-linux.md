---
title: macOS または Linux でのクライアント アナライザーの実行
description: macOS または Linux でMicrosoft Defender for Endpointクライアント アナライザーを実行する方法について説明します
keywords: クライアント アナライザー, センサーのトラブルシューティング, アナライザー, mdeanalyzer, macos, linux, mdeanalyzer
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
ms.collection: m365-security-compliance
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 3e7490f4f7141aaf5c350a146c56de2432d58d21
ms.sourcegitcommit: 6bff75867764335685f972943170c7db46e33a6f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/10/2022
ms.locfileid: "67300391"
---
# <a name="run-the-client-analyzer-on-macos-and-linux"></a>macOS または Linux でクライアント アナライザーを実行する


**適用対象:**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

## <a name="running-the-analyzer-through-gui-scenario"></a>GUI シナリオを使用したアナライザーの実行

1. 調査する必要がある macOS または Linux コンピューターに [XMDE クライアント アナライザー](https://aka.ms/XMDEClientAnalyzer) ツールをダウンロードします。

   > [!NOTE]
   > 上記のリンクからダウンロードされた 'XMDEClientAnalyzer.zip' の現在の SHA256 ハッシュは、'bf102a79626c88fe58b5be3034640835f96f5423029292486716d72f515875966c' です。

2. コンピューター上の MDEClientAnalyzer.zip の内容を抽出します。

3. ターミナル セッションを開き、ディレクトリを抽出された場所に変更してから実行します。

   `./mde_support_tool.sh -d`

   > [!NOTE]
   > Linux では、スクリプトに実行アクセス許可がない場合は、最初に実行する必要があります。
   >
   > `chmod a+x mde_support_tool.sh`

## <a name="running-the-analyzer-using-a-terminal-or-ssh-scenario"></a>ターミナルまたは SSH シナリオを使用したアナライザーの実行

関連するコンピューターにターミナルまたは SSH を開き、次のコマンドを実行します。

1. `wget --quiet -O XMDEClientAnalyzer.zip https://aka.ms/XMDEClientAnalyzer`

2. `unzip -q XMDEClientAnalyzer.zip`

3. `cd XMDEClientAnalyzer`

4. `chmod +x mde_support_tool.sh`

3. 必要な pip コンポーネントと lxml コンポーネントをインストールするために、ルート以外の使用として実行します。 `./mde_support_tool.sh`

4. 実際の診断パッケージを収集し、結果アーカイブ ファイルを生成するには、ルートとして再実行します。 `./mde_support_tool.sh -d`

> [!NOTE]
> - Linux の場合、アナライザーは結果出力を生成するために 'lxml' を必要とします。 インストールされていない場合、アナライザーは、以下の Python パッケージの公式リポジトリからそれをフェッチしようとします。 <https://pypi.org/search/?q=lxml>
> 
> - さらに、このツールでは現在、Python バージョン 3 以降をインストールする必要があります。
>
> - Python 3 を使用できないコンピューターまたは lxml コンポーネントをフェッチできないマシンで実行している場合は、 [XMDE クライアント アナライザー バイナリ](https://aka.ms/XMDEClientAnalyzerBinary)という要件を持たないバイナリ ベースのバージョンのアナライザーをダウンロードできます。 <br> バイナリは現在署名されていません。 MacOS でパッケージを実行できるようにするには、"spctl --add /Path/To/Application.app" という構文を使用する必要があります。
> - 上記のリンクからダウンロードされた 'XMDEClientAnalyzerBinary.zip' の現在の SHA256 ハッシュは、'7FE67373CDF493BF2748FD778BD106EE85A71C968D594BCC67C7374620506EF2' です。
>
> - デバイスがプロキシの背後にある場合は、プロキシ サーバーを環境変数としてmde_support_tool.sh スクリプトに渡すだけです。 例: `https_proxy=https://myproxy.contoso.com:8080 ./mde_support_tool.sh"`

例:

:::image type="content" source="images/4ca188f6c457e335abe3c9ad3eddda26.png" alt-text="コマンド ラインの例" lightbox="images/4ca188f6c457e335abe3c9ad3eddda26.png":::

その他の構文ヘルプ:

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

## <a name="result-package-contents-on-macos-and-linux"></a>macOS と Linux 上の結果パッケージの内容

- report.html

  説明: アナライザー スクリプトがコンピューターで実行できる結果とガイダンスを含むメイン HTML 出力ファイル。

- mde_diagnostic.zip

  説明: いずれかの [macOS](/windows/security/threat-protection/microsoft-defender-atp/mac-resources#collecting-diagnostic-information) で *mdatp 診断の作成* を実行するときに生成されるのと同じ診断出力

  または

  [ Linux ](/windows/security/threat-protection/microsoft-defender-atp/linux-resources#collect-diagnostic-information)

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
