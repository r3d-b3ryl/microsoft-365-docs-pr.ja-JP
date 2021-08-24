---
title: macOS または Linux でのクライアント アナライザーの実行
description: macOS または Linux で Microsoft Defender for Endpoint Client Analyzer を実行する方法について説明します。
keywords: クライアント アナライザー、センサー、アナライザー、mdeanalyzer、macos、Linux、mdeanalyzer のトラブルシューティング
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
ms.openlocfilehash: dd103e31924c892eb7f43bc89c5a17f9721cea12
ms.sourcegitcommit: 4582873483bd52bc790bf75b838cc505dc4bbeb4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/24/2021
ms.locfileid: "58502065"
---
#  <a name="run-the-client-analyzer-on-macos-and-linux"></a>macOS または Linux でクライアント アナライザーを実行する

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2146631)


## <a name="running-the-analyzer-through-gui-scenario"></a>GUI シナリオによるアナライザーの実行

1.  調査する [必要がある macOS](https://aka.ms/XMDEClientAnalyzer) または Linux コンピューターに XMDE クライアント アナライザー ツールをダウンロードします。
> [!NOTE]  
> 上記のリンクからダウンロードされる 'XMDEClientAnalyzer.zip' の現在の SHA256 ハッシュは、'029296D437BA97B5563D0C75DD874F8F51C563B2B5AC16745619F4DB2E064C85'です。

2.  コンピューター上のXMDEClientAnalyzer.zipを抽出します。

3.  ターミナル セッションを開き、ディレクトリを抽出した場所に変更し、次のコマンドを実行します。

`./mde_support_tool.sh -d`

!メモ  
Linux では、スクリプトに実行するアクセス許可が付与されていない場合は、最初に次のコマンドを実行する必要があります。  
*chmod a+x mde_support_tool.sh*

## <a name="running-the-analyzer-using-a-terminal-or-ssh-scenario"></a>ターミナルまたは SSH シナリオを使用してアナライザーを実行する

1.  ターミナルまたは SSH を関連するコンピューターに開きます。

2.  `wget --quiet -O XMDEClientAnalyzer.zip*
    <https://aka.ms/XMDEClientAnalyzer> *&& unzip -q XMDEClientAnalyzer.zip && cd
    XMDEClientAnalyzer && chmod +x mde_support_tool.sh"` を実行します。

3.  結果 ` ./mde_support_tool.sh -d ` アーカイブ ファイルを生成するために実行します。

> [!NOTE]  
> Linux の場合、アナライザーは結果出力を生成するために 'lxml' を必要とします。 インストールされていない場合、アナライザーは以下の Python パッケージの公式リポジトリから取得します。  
https://files.pythonhosted.org/packages/\*/lxml .whl また、現在、ツールのインストールには \* Python バージョン 3 以降が必要です。

例:  


![コマンド ラインの例のイメージ](images/4ca188f6c457e335abe3c9ad3eddda26.png)

  
  
その他の構文ヘルプ:

**-h** \# ヘルプ  
\# ヘルプ メッセージを表示する

**-p** \# パフォーマンス  
\# まだ実装されていない計画されたパラメーター。  
\# オンデマンドで再現できるパフォーマンスの問題を分析するために、広範なトレースを収集します。

**-o** \# 出力  
\# 結果ファイルの宛先パスを指定する

**-nz** \# No-Zip  
\# 設定すると、結果のアーカイブ ファイルの代わりにディレクトリが作成されます

**-f** \# Force  
\# 出力が宛先パスに既に存在する場合は上書きする

## <a name="result-package-contents-on-macos-and-linux"></a>macOS および Linux の結果パッケージの内容

-   report.html <br> 説明: アナライザー スクリプトがコンピューターで実行できる結果とガイダンスを含むメインの HTML 出力ファイル。

-   mde_diagnostic.zip <br> 説明: [macOS](/windows/security/threat-protection/microsoft-defender-atp/mac-resources#collecting-diagnostic-information)または Linux で *mdatp* 診断作成を実行するときに生成される診断出力と同 [じ](/windows/security/threat-protection/microsoft-defender-atp/linux-resources#collect-diagnostic-information)

-   mde.xml <br> 説明: 実行中に生成され、HTML レポート ファイルのビルドに使用される XML 出力。

-   Processes_information.txt <br> 説明: システムで実行中の Microsoft Defender for Endpoint 関連プロセスの詳細が含まれる。

-   Log.txt <br> 説明: データ収集中に画面に書き込まれた同じログ メッセージが含まれます。

-   Health.txt <br> 説明: mdatp health コマンドを実行するときに表示されるのと同じ基本的 *な正常性出力* 。

-   Events.xml <br> 説明: HTML レポートの作成時にアナライザーによって使用される追加の XML ファイル。

-   Auditd_info.txt <br> 説明: Linux OS の監査されたサービスと関連コンポーネント [の](/windows/security/threat-protection/microsoft-defender-atp/linux-support-events) 詳細
