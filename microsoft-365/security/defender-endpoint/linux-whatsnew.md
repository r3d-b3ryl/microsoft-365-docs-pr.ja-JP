---
title: Linux でのMicrosoft Defender for Endpointの新機能
description: Linux でのMicrosoft Defender for Endpointの主な変更点の一覧。
keywords: microsoft, defender, Microsoft Defender for Endpoint, linux, whatsnew, release
ms.prod: m365-security
ms.mktglfcycl: security
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
ms.topic: reference
ms.technology: mde
ms.openlocfilehash: ea99a46d468e6c3d5e7346006da0eb24116067d0
ms.sourcegitcommit: d1b60ed9a11f5e6e35fbaf30ecaeb9dfd6dd197d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/29/2022
ms.locfileid: "66489949"
---
# <a name="whats-new-in-microsoft-defender-for-endpoint-on-linux"></a>Linux でのMicrosoft Defender for Endpointの新機能

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)


この記事は、Linux 上のMicrosoft Defender for Endpointの最新リリースの新機能を知るために頻繁に更新されます。 

- [macOS 上の Defender for Endpoint の新機能](mac-whatsnew.md)
- [iOS 上の Defender for Endpoint の新機能](ios-whatsnew.md)

<details>
  <summary>2022 年 6 月 (ビルド: 101.71.18 |リリース バージョン: 30.122052.17118.0)</summary>

&ensp;リリース **日: 2022 年 6 月 24** 日<br/>
&ensp;発行日: **2022 年 6 月 24** 日<br/>
&ensp;ビルド: **101.71.18**<br/>
&ensp;リリース バージョン: **30.122042.16880.0**<br/>


**新機能**

- RHEL 6 で使用されている製品センサーで、OS がハングする可能性がある問題を修正しました
- `mdatp connectivity test` は、製品が正しく機能するために必要な追加の URL で拡張されました。 新しい URL は [https://go.microsoft.com/fwlink/?linkid=2144709](https://go.microsoft.com/fwlink/?linkid=2144709).
- これまで、製品の再起動の間、製品ログ レベルは保持されませんでした。 このバージョン以降、ログ レベルを保持する新しいコマンド ライン ツール スイッチがあります。 新しいコマンドは .`mdatp log level persist --level <level>`
- 製品インストール パッケージから依存関係 `python` を削除しました
- ファイル コピー操作のパフォーマンスの向上と、元のネットワーク イベントの処理 `auditd`
- バグ修正
</br>

<br/><br/>
</details>


<details>
  <summary>2022 年 5 月 (ビルド: 101.68.80 |リリース バージョン: 30.122042.16880.0)</summary>

&ensp;リリース日: **2022 年 5 月 23** 日<br/>
&ensp;発行日: **2022 年 5 月 23** 日<br/>
&ensp;ビルド: **101.68.80**<br/>
&ensp;リリース バージョン: **30.122042.16880.0**<br/>

**新機能** 

- RHEL 6 で実行するときのカーネル バージョン `2.6.32-754.47.1.el6.x86_64` のサポートを追加しました
- RHEL 6 で、壊れないエンタープライズ カーネル (UEK) を実行しているデバイスに製品をインストールできるようになりました
- 実行中と同じように `unknown` プロセス名が正しく表示されない問題を修正しました `mdatp diagnostic real-time-protection-statistics`
- 製品が検疫フォルダー内のファイルを誤って検出する場合があるバグを修正しました
- ソフト リンクとしてマウントされたときにコマンド ライン ツールが`/opt`機能しない問題`mdatp`を修正しました
- バグ修正&パフォーマンスの向上
</br>

<br/><br/>
</details>

<details>
<summary>2022 年 5 月 (ビルド: 101.65.77 |リリース バージョン: 30.122032.16577.0)</summary>

&ensp;リリース日: **2022 年 5 月 2 日**<br/>
&ensp;発行日: **2022 年 5 月 2 日**<br/>
&ensp;ビルド: **101.65.77**<br/>
&ensp;リリース バージョン: **30.122032.16577.0**<br/>


**新機能**

- フィールド`mdatp health`を`conflicting_applications`改善し、最新の 10 個のプロセスのみを表示し、プロセス名を含める必要があります。 これにより、Linux のMicrosoft Defender for Endpointと競合する可能性があるプロセスを簡単に特定できます。
- バグ修正


<br/><br/>
</details><details>
<summary>Mar-2022 (ビルド: 101.62.74 |リリース バージョン: 30.122022.16274.0)</summary>

&ensp;リリース日: **2022 年 3 月 24** 日<br/>
&ensp;発行日: **2022 年 3 月 24** 日<br/>
&ensp;ビルド: **101.62.74**<br/>
&ensp;リリース バージョン: **30.122022.16274.0**<br/>


**新機能**

- 以前のカーネル バージョンで実行しているときに、製品がサイズが 2 GB を超えるファイルへのアクセスを誤ってブロックする問題に対処しました
- バグ修正


<br/><br/>
</details><details>
<summary>Mar-2022 (ビルド: 101.60.93 |リリース バージョン: 30.122012.16093.0)</summary>

&ensp;リリース日: **2022 年 3 月 9** 日<br/>
&ensp;発行日: **2022 年 3 月 9** 日<br/>
&ensp;ビルド: **101.60.93**<br/>
&ensp;リリース バージョン: **30.122012.16093.0**<br/>

**新機能**

- このバージョンには[、CVE-2022-23278](https://msrc-blog.microsoft.com/2022/03/08/guidance-for-cve-2022-23278-spoofing-in-microsoft-defender-for-endpoint/) のセキュリティ更新プログラムが含まれています


<br/><br/>
</details><details>
<summary>Mar-2022 (ビルド: 101.60.05 |リリース バージョン: 30.122012.16005.0)</summary>

&ensp;リリース日: **2022 年 3 月 3** 日<br/>
&ensp;発行日: **2022 年 3 月 3** 日<br/>
&ensp;ビルド: **101.60.05**<br/>
&ensp;リリース バージョン: **30.122012.16005.0**<br/>

**新機能**

- RHEL 6.10 のカーネル バージョン 2.6.32-754.43.1.el6.x86_64のサポートを追加しました
- バグ修正


<br/><br/>
</details><details>
<summary>2022 年 2 月 (ビルド: 101.58.80 |リリース バージョン: 30.122012.15880.0)</summary>

&ensp;リリース **日: 2022 年 2 月 20 日**<br/>
&ensp;発行日: **2022 年 2 月 20 日**<br/>
&ensp;ビルド: **101.58.80**<br/>
&ensp;リリース バージョン: **30.122012.15880.0**<br/>

**新機能**

- コマンド ライン ツールでは、検疫されたファイルを、ファイルが最初に検出された場所以外の場所に復元できるようになりました。 これは 、 `mdatp threat quarantine restore --id [threat-id] --path [destination-folder]`.
- このバージョン以降、Linux のネットワーク保護をオンデマンドで評価できます
- バグ修正



<br/><br/>
</details><details>
<summary>2022 年 1 月 (ビルド: 101.56.62 |リリース バージョン: 30.121122.15662.0)</summary>

&ensp;リリース日: **2022 年 1 月 26** 日<br/>
&ensp;発行日: **2022 年 1 月 26** 日<br/>
&ensp;ビルド: **101.56.62**<br/>
&ensp;リリース バージョン: **30.121122.15662.0**<br/>

**新機能**

- 101.53.02 で発生し、複数の顧客に影響を与えた製品のクラッシュを修正しました


<br/><br/>
</details><details>
<summary>2022 年 1 月 (ビルド: 101.53.02 |リリース バージョン: (30.121112.15302.0)</summary>

&ensp;リリース日: **2022 年 1 月 8** 日<br/>
&ensp;発行日: **2022 年 1 月 8** 日<br/>
&ensp;ビルド: **101.53.02**<br/>
&ensp;リリース バージョン: **30.121112.15302.0**<br/>

**新機能**

- バグ修正&パフォーマンスの向上



</details>

<details><summary> 2021 リリース</summary><blockquote>
  <details><summary>(ビルド: 101.52.57 |リリース バージョン: 30.121092.15257.0)</summary>
   
  <p><b> ビルド: 101.52.57 <br>
リリース バージョン: 30.121092.15257.0</b></p>
   
  <p><b> 新機能 </b></p>

   - Java アプリケーションで使用されている脆弱な log4j jar を検出する機能を追加しました。 マシンは、読み込まれた log4j jar で Javaprocesses を実行するために定期的に検査されます。 この情報はMicrosoft Defender for Endpoint バックエンドに報告され、ポータルのVulnerability Management 領域で公開されます。
   
   </details>

  <details><summary>(ビルド: 101.47.76 |リリース バージョン: 30.121092.14776.0)</summary>
   
  <p><b> ビルド: 101.47.76 <br>
リリース バージョン: 30.121092.14776.0</b></p>
   
  <p><b>新機能</b></p>

   - オンデマンド スキャン中にアーカイブをスキャンするかどうかを制御する新しいスイッチをコマンド ライン ツールに追加しました。 これは、mdatp config scan-archives --value [enabled/disabled]を使用して構成できます。 既定では、これは有効に設定されています。

   - バグ修正

   </details>

   <details><summary>(ビルド: 101.45.13 |リリース バージョン: 30.121082.14513.0)</summary>
   
  <p> 
  ビルド: <b>101.45.13 </b>  <br>
リリース バージョン:<b> 30.121082.14513.0 </b></p>
   
  <p><b>新機能</b></p>

  - このバージョン以降、次のディストリビューションにMicrosoft Defender for Endpointサポートを提供しています。

    - RHEL6.7-6.10 および CentOS6.7-6.10 バージョン。
    - Amazon Linux 2
    - Fedora 33 以降

  - バグ修正

   </details>


   <details><summary>(ビルド: 101.45.00 |リリース バージョン: 30.121072.14500.0)</summary>
   
   <p> 
   ビルド:<b> 101.45.00</b> <br>
リリース バージョン: <b>30.121072.14500.0</b></p>
   
   <p><b>新機能</b></p>
      

  - コマンド ライン ツールに新しいスイッチを追加しました。
    - オンデマンド スキャンの並列処理の度合いを制御します。 これを構成 `mdatp config maximum-on-demand-scan-threads --value [number-between-1-and-64]`するには、 . 既定では、ある程度の並列処理 `2` が使用されます。
    - セキュリティ インテリジェンスの更新後のスキャンを有効または無効にするかどうかを制御します。 これを構成 `mdatp config scan-after-definition-update --value [enabled/disabled]`するには、 . 既定では、これは `enabled`.
  - 製品ログ レベルを変更するには、昇格が必要になりました
  - バグ修正

   </details>

   <details><summary>(ビルド: 101.39.98 |リリース バージョン: 30.121062.13998.0)</summary>
   
   <p> 
   ビルド: <b>101.39.98 </b><br>
リリース バージョン: <b>30.121062.13998.0</b></p>
   
   <p><b>新機能</b></p>

  - バグ修正&パフォーマンスの向上
  
   </details>

   <details><summary>(ビルド: 101.34.27 |リリース バージョン: 30.121052.13427.0)</summary>
   
   <p> 
   ビルド:<b> 101.34.27</b> <br>
リリース バージョン: <b>30.121052.13427.0</b></p>
   
   <p><b>新機能</b></p>

   - バグ修正&パフォーマンスの向上
  
   </details>

   <details><summary>(ビルド: 101.29.64 |リリース バージョン: 30.121042.12964.0)</summary>
   
   <p> 
   ビルド:<b> 101.29.64 </b><br>
リリース バージョン:<b> 30.121042.12964.0</b></p>
   
   <p><b>新機能</b></p>

   - このバージョン以降、コマンド ライン クライアントを介してトリガーされたオンデマンドウイルス対策スキャン中に検出された脅威は自動的に修復されます。 ユーザー インターフェイスを介してトリガーされたスキャン中に検出された脅威には、手動操作が必要です。
   - `mdatp diagnostic real-time-protection-statistics` 次の 2 つの追加スイッチがサポートされるようになりました。
     - `--sort`: 出力を降順に並べ替え、スキャンされたファイルの合計数で並べ替えます。
     - `--top N`: 上位 N 個の結果が表示されます (指定されている場合 `--sort` にのみ機能します)
   - バグ修正&パフォーマンスの向上
  
   </details>

   <details><summary>(ビルド: 101.25.72 |リリース バージョン: 30.121022.12563.0)</summary>
   
   <p> 
   ビルド:<b> 101.25.72</b> <br>
リリース バージョン: <b>30.121022.12563.0</b></p>
   
   <p><b>新機能</b></p>

   - Linux 上のMicrosoft Defender for Endpointは、米国政府機関のお客様向けのプレビューで利用できるようになりました。 詳細については、「[米国政府機関のお客様向けのMicrosoft Defender for Endpoint」を参照してください](gov.md)。
   - FUSE ファイルシステムを使用するシステムで Linux でMicrosoft Defender for Endpointを使用すると OS がハングする問題を修正しました
   - その他のバグ修正&パフォーマンスの向上
  
   </details>

   
   <details><summary>(ビルド: 101.25.63 |リリース バージョン: 30.121022.12563.0)</summary>
   
   <p> 
   ビルド:<b> 101.25.63</b> <br>
リリース バージョン: <b>30.121022.12563.0</b></p>
   
   <p><b>新機能</b></p>

   - バグ修正&パフォーマンスの向上
  
   </details>

   <details><summary>(ビルド: 101.23.64 |リリース バージョン: 30.121021.12364.0)</summary>
   
   <p>
ビルド:<b> 101.23.64 </b><br>
リリース バージョン: 30.121021.12364.0</b></p>
   
   <p><b>新機能</b></p>

   - マウント ポイント全体がウイルス対策除外リストに追加される状況のパフォーマンスが向上しました。 このバージョンより前のバージョンでは、マウント ポイントから発生したファイル アクティビティは、製品によって処理されていました。 このバージョン以降、除外されたマウント ポイントのファイル アクティビティが抑制され、製品のパフォーマンスが向上します
   - 最後のオンデマンド スキャンに関する情報を表示する新しいオプションをコマンド ライン ツールに追加しました。 最後のオンデマンド スキャンに関する情報を表示するには、次のコマンドを実行します。 `mdatp health --details antivirus`
   - バグ修正&その他のパフォーマンスの向上
  
   </details>

   <details><summary>(ビルド: 101.18.53)</summary>
   
    <p> 
    ビルド:<b> 101.18.53 </b><br>
        
    <p>新機能</b></p>

   - EDR for Linux が[一般公開](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/edr-for-linux-is-now-is-generally-available/ba-p/2048539)されました
   - カスタム スキャン中に AV 除外を無視する新しいコマンド ライン スイッチ (`--ignore-exclusions`) を追加しました (`mdatp scan custom`)
   - `mdatp diagnostic create`診断ログを別のディレクトリに保存できるようにする新しいパラメーター (`--path [directory]`) で拡張
    - バグ修正&パフォーマンスの向上
    
   </details>





</blockquote></details>

