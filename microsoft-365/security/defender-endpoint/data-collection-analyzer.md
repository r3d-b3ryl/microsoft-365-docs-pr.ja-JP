---
title: Windows で高度なトラブルシューティングを行うためのデータ収集
description: クライアント アナライザーを使用して、複雑なトラブルシューティング シナリオのデータを収集する方法について説明します
keywords: analzyer, データの収集, mdeclientanalyzer のトラブルシューティング, 高度なトラブルシューティング
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
ms.openlocfilehash: 2825bc87750dc9bb130e35f9a4997283e470f869
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2022
ms.locfileid: "64469891"
---
# <a name="data-collection-for-advanced-troubleshooting-on-windows"></a>Windows で高度なトラブルシューティングを行うためのデータ収集

**適用対象:**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

Microsoft サポート担当者と協力する場合は、クライアント アナライザーを使用して、より複雑なシナリオのトラブルシューティングのためにデータを収集するように求められる場合があります。 アナライザー スクリプトは、その目的で他のパラメーターをサポートし、調査する必要がある観察された現象に基づいて特定のログ セットを収集できます。

'**MDEClientAnalyzer.cmd /?**' を実行する 使用可能なパラメーターとその説明の一覧を表示するには:

:::image type="content" source="images/d89a1c04cf8441e4df72005879871bd0.png" alt-text="MDEClientAnalyzer.cmd のパラメーター" lightbox="images/d89a1c04cf8441e4df72005879871bd0.png":::

> [!NOTE]
> 高度なトラブルシューティング パラメーターを使用すると、アナライザーは[MpCmdRun.exe](/microsoft-365/security/defender-endpoint/command-line-arguments-microsoft-defender-antivirus)を呼び出して、関連するサポート ログMicrosoft Defender ウイルス対策収集します。

**-h** - [Windows パフォーマンス レコーダー](/windows-hardware/test/wpt/wpr-command-line-options)を呼び出して、標準ログ セットに加えて詳細な一般的なパフォーマンス トレースを収集します。

**-l** - 組み込みの [Windows パフォーマンス モニター](/windows-server/remote/remote-desktop-services/rds-rdsh-performance-counters)を呼び出して、軽量の perfmon トレースを収集します。 これは、時間の経過と共に発生するパフォーマンス低下の問題を診断するが、オンデマンドで再現するのが難しい場合に役立つ場合があります。

**-c** - [プロセス モニター](/sysinternals/downloads/procmon) を呼び出して、リアルタイム のファイル システム、レジストリ、およびプロセス/スレッド アクティビティを高度に監視します。 これは、さまざまなアプリケーション互換性シナリオのトラブルシューティングに特に役立ちます。

**-i** - 組み込みの [netsh.exe](/windows/win32/winsock/netsh-exe) コマンドを呼び出して、ネットワーク関連のさまざまな問題のトラブルシューティングに役立つネットワークと Windows ファイアウォール トレースを開始します。

**-b** - '-c' と同じですが、プロセス モニター トレースは次回の起動時に開始され、-b が再度使用された場合にのみ停止します。

**-a** - [Windows パフォーマンス レコーダー](/windows-hardware/test/wpt/wpr-command-line-options)を呼び出して、ウイルス対策プロセス (MsMpEng.exe) に関連する CPU の高い問題の分析に固有の詳細なパフォーマンス トレースを収集します。

**-v** - ウイルス対策 [MpCmdRun.exeコマンド ライン引数](/windows/security/threat-protection/microsoft-defender-antivirus/command-line-arguments-microsoft-defender-antivirus) を使用し、最も詳細な -trace フラグを使用します。

**-t** - エンドポイント DLP に関連するすべてのクライアント側コンポーネントの詳細トレースを開始します。 これは、ファイルに対して [DLP アクション](/microsoft-365/compliance/endpoint-dlp-learn-about#endpoint-activities-you-can-monitor-and-take-action-on) が想定どおりに実行されないシナリオに便利です。

**-q** - Endpoint DLP の基本的な構成と要件を検証するアナライザー 'Tools' ディレクトリから、DLPDiagnose.ps1 スクリプトを呼び出します。

**-d** - **MsSenseS**.exe (Windows Server 2016 以前の OS 上のセンサー プロセス) および関連するプロセスのメモリ ダンプを収集します。

- \* このフラグは、上記のフラグと組み合わせて使用できます。
- \*\* MsSense.exeやMsMpEng.exeなどの [PPL で保護されたプロセス](/windows-hardware/drivers/install/early-launch-antimalware) のメモリ ダンプのキャプチャは、現時点ではアナライザーではサポートされていません。

**-z** - [CrashOnCtrlScroll](/windows-hardware/drivers/debugger/forcing-a-system-crash-from-the-keyboard) を使用してマシン上のレジストリ キーを構成し、完全なマシン メモリ ダンプ コレクションを準備します。 これは、コンピューターの凍結の問題の分析に役立ちます。

\* 右端の Ctrl キーを押しながら、SCROLL LOCK キーを 2 回押します。

**-k** - [NotMyFault](/sysinternals/downloads/notmyfault) ツールを使用して、システムを強制的にクラッシュさせ、マシン メモリ ダンプを生成します。 これは、さまざまな OS の安定性の問題の分析に役立ちます。

アナライザーと上記のすべてのシナリオ フラグは、アナライザー ツールセットにバンドルされている 'RemoteMDEClientAnalyzer.cmd' を実行してリモートで開始できます。

:::image type="content" source="images/57cab9d82d08f672a92bf9e748ac9572.png" alt-text="RemoteMDEClientAnalyzer.cmd のパラメーター" lightbox="images/57cab9d82d08f672a92bf9e748ac9572.png":::

> [!NOTE]
>
> - RemoteMDEClientAnalyzer.cmd を使用する場合、psexec を呼び出して構成されたファイル共有からツールをダウンロードし、PsExec.exe経由でローカルで実行します。
    CMD スクリプトでは、'-r' フラグを使用して、SYSTEM コンテキスト内でリモートで実行されているため、ユーザーに対するプロンプトは表示されません。
> - 同じフラグを MDEClientAnalyzer.cmd と共に使用すると、データ収集の分数の指定を要求するユーザーへのプロンプトを回避できます。 次に、例を示します。
>
>    **MDEClientAnalyzer.cmd -r -i -m 5**
>
>   - **-r** - ツールがリモート (または非対話型コンテキスト) から実行されていることを示します
>   - **-i** - 他の関連ログと共にネットワーク トレースを収集するためのシナリオ フラグ
>   - **-m** \# - 実行する分数 (上記の例では 5 分)
