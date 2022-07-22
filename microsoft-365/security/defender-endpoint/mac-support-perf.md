---
title: macOS でのMicrosoft Defender for Endpointのパフォーマンスの問題のトラブルシューティング
description: macOS でのMicrosoft Defender for Endpointのパフォーマンスの問題のトラブルシューティングを行います。
keywords: microsoft、Defender、Microsoft Defender for Endpoint、mac、パフォーマンス
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 7c60a61ca1a0a1179abd27c0f6d59970a0c09866
ms.sourcegitcommit: 00948161a72d8cea8c2baba873743fc4a0e19f90
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/22/2022
ms.locfileid: "66969554"
---
# <a name="troubleshoot-performance-issues-for-microsoft-defender-for-endpoint-on-macos"></a>macOS でのMicrosoft Defender for Endpointのパフォーマンスの問題のトラブルシューティング

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**

- [macOS 用 Microsoft Defender for Endpoint](microsoft-defender-endpoint-mac.md)
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

このトピックでは、macOS でのMicrosoft Defender for Endpointに関連するパフォーマンスの問題を絞り込むために使用できる一般的な手順について説明します。

リアルタイム保護 (RTP) は、デバイスを脅威から継続的に監視および保護する macOS 上のMicrosoft Defender for Endpointの機能です。 ファイルとプロセスの監視とその他のヒューリスティックで構成されます。

実行しているアプリケーションとデバイスの特性によっては、macOS でMicrosoft Defender for Endpointを実行するときに最適でないパフォーマンスが発生する場合があります。 特に、短時間で多くのリソースにアクセスするアプリケーションまたはシステム プロセスは、macOS 上のMicrosoft Defender for Endpointのパフォーマンスの問題につながる可能性があります。

これらの問題のトラブルシューティングと軽減には、次の手順を使用できます。

1. 次のいずれかの方法を使用してリアルタイム保護を無効にし、パフォーマンスが向上するかどうかを確認します。 このアプローチは、macOS 上のMicrosoft Defender for Endpointがパフォーマンスの問題に貢献しているかどうかを絞り込むのに役立ちます。

      デバイスが組織によって管理されていない場合は、次のいずれかのオプションを使用してリアルタイム保護を無効にすることができます。

    - ユーザー インターフェイスから。 macOS でMicrosoft Defender for Endpointを開き、[**設定の管理]** に移動します。

      :::image type="content" source="images/mdatp-36-rtp.png" alt-text=" [リアルタイム保護の管理] ページ" lightbox="images/mdatp-36-rtp.png":::
      

    - ターミナルから。 セキュリティ上の理由から、この操作には昇格が必要です。

      ```bash
      mdatp config real-time-protection --value disabled
      ```

      デバイスが組織によって管理されている場合は、「[macOS でMicrosoft Defender for Endpointの環境設定を設定](mac-preferences.md)する」の手順を使用して、管理者がリアルタイム保護を無効にすることができます。

      リアルタイム保護がオフの間もパフォーマンスの問題が解決しない場合、問題の原因はエンドポイントの検出と応答コンポーネントである可能性があります。 この場合は、詳細な手順と軽減策については、カスタマー サポートにお問い合わせください。

2. Finder を開き、 **アプリケーション** \> ユーティリティに移動 **します**。 **アクティビティ モニターを** 開き、システム上のリソースを使用しているアプリケーションを分析します。 一般的な例には、ソフトウェア アップデーターとコンパイラが含まれます。

3. 最もスキャンをトリガーしているアプリケーションを見つけるには、Defender for Endpoint on Mac によって収集されたリアルタイム統計を使用できます。

      > [!NOTE]
      > この機能は、バージョン 100.90.70 以降で使用できます。
      この機能は、 **Dogfood** チャネルと **InsiderFast** チャネルで既定で有効になっています。 別の更新チャネルを使用している場合は、コマンド ラインからこの機能を有効にすることができます。

      ```bash
      mdatp config real-time-protection-statistics  --value enabled
      ```

      この機能を有効にするには、リアルタイムの保護が必要です。 リアルタイム保護の状態を確認するには、次のコマンドを実行します。

      ```bash
      mdatp health --field real_time_protection_enabled
      ```

    **real_time_protection_enabled** エントリが true であることを確認します。 それ以外の場合は、次のコマンドを実行して有効にします。

      ```bash
      mdatp config real-time-protection --value enabled
      ```

      ```output
      Configuration property updated
      ```

      現在の統計を収集するには、次のコマンドを実行します。

      ```bash
      mdatp diagnostic real-time-protection-statistics --output json > real_time_protection.json
      ```

      > [!NOTE]
      > **--output json** (二重ダッシュに注意) を使用すると、出力形式を解析する準備が整います。
      このコマンドの出力には、すべてのプロセスとそれに関連するスキャン アクティビティが表示されます。

4. Mac システムで、次のコマンドを使用してサンプル Python パーサー high_cpu_parser.py をダウンロードします。

    ```bash
    curl -O https://raw.githubusercontent.com/microsoft/mdatp-xplat/master/linux/diagnostic/high_cpu_parser.py
    ```

    このコマンドの出力は、次のようになります。

    ```Output
    --2020-11-14 11:27:27-- https://raw.githubusercontent.com/microsoft.
    mdatp-xplat/master/linus/diagnostic/high_cpu_parser.py
    Resolving raw.githubusercontent.com (raw.githubusercontent.com)... 151.101.xxx.xxx
    Connecting to raw.githubusercontent.com (raw.githubusercontent.com)| 151.101.xxx.xxx| :443... connected.
    HTTP request sent, awaiting response... 200 OK
    Length: 1020 [text/plain]
    Saving to: 'high_cpu_parser.py'
    100%[===========================================>] 1,020    --.-K/s   in
    0s
    ```

5. 次に、次のコマンドを入力します。

      ```bash
        chmod +x high_cpu_parser.py
      ```

      ```bash
        cat real_time_protection.json | python high_cpu_parser.py  > real_time_protection.log
      ```

      上記の出力は、パフォーマンスの問題に対する主要な貢献者の一覧です。 最初の列はプロセス識別子 (PID)、2 番目の列はプロセス名、最後の列はスキャンされたファイルの数で、影響によって並べ替えられます。

      たとえば、コマンドの出力は次のようになります。

      ```output
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

      Mac 上の Defender for Endpoint のパフォーマンスを向上させるには、[スキャンされたファイルの合計数] 行の下の数値が最も高いものを見つけ、除外を追加します。 詳細については、「 [macOS 上の Defender for Endpoint の除外を構成して検証する」を](mac-exclusions.md)参照してください。

      > [!NOTE]
      > アプリケーションは、メモリに統計を格納し、ファイルアクティビティが開始され、リアルタイム保護が有効になっているため、ファイル アクティビティのみを追跡します。 リアルタイム保護がオフになっていた期間の前または期間中に起動されたプロセスはカウントされません。 さらに、トリガーされたスキャンのイベントのみがカウントされます。
      >
6. パフォーマンスの問題に影響するプロセスまたはディスクの場所を除外して macOS でMicrosoft Defender for Endpointを構成し、リアルタイム保護を再度有効にします。

     詳細については、「[macOS でのMicrosoft Defender for Endpointの除外の構成と検証](mac-exclusions.md)」を参照してください。
