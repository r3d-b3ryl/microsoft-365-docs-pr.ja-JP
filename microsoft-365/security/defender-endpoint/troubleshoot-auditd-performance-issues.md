---
title: Linux 上のMicrosoft Defender for Endpointに関する AuditD パフォーマンスの問題のトラブルシューティング
ms.reviewer: ''
description: Microsoft Defender for Linux で発生する可能性がある AuditD 関連のパフォーマンスの問題をトラブルシューティングする方法について説明します。
keywords: microsoft, defender, Microsoft Defender for Endpoint, Linux, トラブルシューティング, AuditD, XMDEClientAnalyzer, インストール, デプロイ, アンインストール
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
ms.openlocfilehash: 31aaf297fd3622eede2e1532ad60a20666d1bd07
ms.sourcegitcommit: 49c275f78664740988bbc4ca4b14d3ad758e1468
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/19/2022
ms.locfileid: "66882894"
---
# <a name="troubleshoot-auditd-performance-issues-with-microsoft-defender-for-endpoint-on-linux"></a>Linux 上のMicrosoft Defender for Endpointに関する AuditD パフォーマンスの問題のトラブルシューティング 

この記事では、Linux 上のMicrosoft Defender for Endpointで発生する可能性がある AuditD 関連のパフォーマンスの問題をトラブルシューティングする方法に関するガイダンスを提供します。 

**背景：** 

- Linux OS ディストリビューションのMicrosoft Defender for Endpointでは、AuditD フレームワークを使用して特定の種類のテレメトリ イベントを収集します。 

- 追加 `/etc/audit/rules.d/` された規則によってキャプチャされたシステム イベントは audit.log に追加され、ホストの監査とアップストリームの収集に影響を与える可能性があります。  

- Linux でMicrosoft Defender for Endpointによって追加されたイベントには、キーがタグ付`mdatp`けされます。 

- AuditD サービスが正しく構成されていないかオフラインの場合、一部のイベントが見つからない可能性があります。 このような問題のトラブルシューティングについては、「[Linux でのMicrosoft Defender for Endpointに関するイベントまたはアラートの不足に関する問題のトラブルシューティング」を](linux-support-events.md)参照してください。

特定のサーバー ワークロードでは、次の 2 つの問題が発生する可能性があります。 

- **_mdatp_audisp_plugin_** プロセスからの **高い CPU** リソース消費量。 

- ***/var/log/audit/audit.log*** が大規模になったり、頻繁にローテーションされたりしています。 

これらの問題は、AuditD が大量に発生するイベントが多いサーバーで発生する可能性があります。  

これは、AuditD のコンシューマーが複数ある場合や、Microsoft Defender for Endpointとサード パーティのコンシューマーを組み合わせたルールが多すぎる場合、または大量のイベントを生成するワークロードが高い場合に発生する可能性があります。 

このような問題のトラブルシューティングを行うには、まず、影響を受けるサンプル サーバーで [MDEClientAnalyzer ログを収集](run-analyzer-macos-linux.md) します。 

> [!NOTE]
> 一般的なベスト プラクティスとして、[Microsoft Defender for Endpoint エージェントを最新の利用可能なバージョンに](linux-whatsnew.md)更新し、さらに調査する前に問題が解決しないかどうかを確認することをお勧めします。


## <a name="xmdeclientanalyzer"></a>XMDEClientAnalyzer 

XMDEClientAnalyzer を使用すると、問題のトラブルシューティングに役立つ分析情報を提供する出力が次のファイルに表示されます。
- auditd_info.txt
- auditd_log_analysis.txt


### <a name="auditd_infotxt"></a>auditd_info.txt

一般的な AuditD 構成が含まれており、次のように表示されます。

- AuditD コンシューマーとして登録されるプロセス。 

- **auditctl -s** output with **enabled=2**  

    - 監査が不変モードであることを示します (構成変更を有効にするには再起動が必要です)。 

- **Auditctl -l** 出力  

    - 現在カーネルに読み込まれているルールが表示されます ("/etc/auditd/rules.d/mdatp.rules" のディスクに存在するルールとは異なる場合があります)。 
    
    - Microsoft Defender for Endpointに関連するルールが表示されます。 
    
### <a name="auditd_log_analysistxt"></a>auditd_log_analysis.txt

AuditD パフォーマンスの問題を調査するときに役立つ重要な集計情報が含まれています。  

- 最も報告されたイベントを所有しているコンポーネント (Microsoft Defender for Endpoint イベントにはタグが付きます`key=mdatp`)。 

- 上位のレポート イニシエーター。 

- 最も一般的なシステム呼び出し (ネットワークイベントやファイルシステム イベントなど)。 

- どのファイル システム パスが最も騒がしいか。 

**ほとんどの AuditD パフォーマンスの問題を軽減するために、AuditD 除外を実装できます。 **

> [!NOTE]
> 除外は、脅威が低く、ノイズの高いイニシエーターまたはパスに対してのみ行う必要があります。 たとえば、大きな盲点を作成するリスクがある /bin/bash を除外しないでください。
> [除外を定義するときに回避する一般的な間違い](/microsoft-365/security/defender-endpoint/common-exclusion-mistakes-microsoft-defender-antivirus)。



## <a name="exclusion-types"></a>除外の種類 

XMDEClientAnalyzer サポート ツールには、AuditD 除外構成規則を追加するために使用できる構文が含まれています。 

AuditD の除外 - ツール構文のヘルプをサポートします。

:::image type="content" source="images/auditd-exclusion-support-tool-syntax-help.png" alt-text="AuditD 除外構成規則の追加に使用できる構文" lightbox="images/auditd-exclusion-support-tool-syntax-help.png":::

**イニシエーター別** 

- **-e/ -exe** 完全バイナリ パス > このイニシエーターによってすべてのイベントを削除します 

**パス別** 

- **-d/ -dir** ディレクトリへの完全パス>このディレクトリを対象とするファイルシステム イベントを削除します 

例: 

"" が "`/opt/app/bin/app``/opt/app/cfg/logs/1234.log`" に書き込まれる場合は、サポート ツールを使用して、さまざまなオプションで除外できます。 

`-e /opt/app/bin/app`

`-d /opt/app/cfg`

`-x /usr/bin/python /etc/usercfg` 

`-d /usr/app/bin/`

その他の例: 

`./mde_support_tool.sh exclude -p <process id>`

`./mde_support_tool.sh exclude -e <process name>`

複数の項目を除外するには、除外を 1 行に連結します。 

`./mde_support_tool.sh exclude -e <process name> -e <process name 2> -e <process name3>`
 
x フラグは、次のように、特定のイニシエーターによるサブディレクトリへのアクセスを除外するために使用されます。 

`./mde_support_tool.sh exclude -x /usr/sbin/mv /tmp`

上記では、mv プロセスによってアクセスされた場合、/tmp サブフォルダーの監視は除外されます。 

 
> [!NOTE]
> AuditD 関連のパフォーマンスの問題の分析と軽減、または大規模な AuditD 除外の展開に関するサポートが必要な場合は、Microsoft サポートにお問い合わせください。 


