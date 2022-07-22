---
title: Mac でのMicrosoft Defender for Endpointの新機能
description: Mac 上の以前のバージョンのMicrosoft Defender for Endpointの主な変更点について説明します。
keywords: microsoft, defender, Microsoft Defender for Endpoint, mac, インストール, macos, whatsnew
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
ms.openlocfilehash: 3ea2822adabcd0a747d34fbdb8c6d8d2c944afdf
ms.sourcegitcommit: 00948161a72d8cea8c2baba873743fc4a0e19f90
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/22/2022
ms.locfileid: "66969542"
---
# <a name="whats-new-in-microsoft-defender-for-endpoint-on-mac"></a>Mac でのMicrosoft Defender for Endpointの新機能

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

他のオペレーティング システムでのMicrosoft Defender for Endpointの詳細については、次の手順を参照してください。 
- [Linux でのMicrosoft Defender for Endpointの新機能](linux-whatsnew.md) 
- [iOS でのMicrosoft Defender for Endpointの新機能](ios-whatsnew.md)</br>

<details>
  <summary>2022 年 7 月 (ビルド: 101.73.77 |リリース バージョン: 20.122062.17377.0)</summary>

&ensp;リリース日: **2022 年 7 月 21** 日<br/>
&ensp;発行日: **2022 年 7 月 21** 日<br/>
&ensp;ビルド: **101.73.77**<br/>
&ensp;リリース バージョン: **20.122062.17377.0**<br/>
&ensp;エンジンバージョン: **1.1.19200.3**<br/>
&ensp;署名バージョン: **1.367.1011.0**<br/>

**新機能**

- ネットワーク拡張機能が原因で印刷を正常に完了できなかった問題に対処しました
- [ファイル ハッシュの計算を構成](mac-preferences.md#configure-file-hash-computation-feature)するオプションを追加しました
- このビルド以降、製品には既定で新しいマルウェア対策エンジンが用意されます
- ファイル コピー操作のパフォーマンスの向上
- バグ修正

<br/>
</details>

<details>
  <summary>2022 年 7 月 (ビルド: 101.71.18 |リリース バージョン: 20.122052.17118.0)</summary>

&ensp;リリース日: **2022 年 7 月 7 日**<br/>
&ensp;発行日: **2022 年 7 月 7 日**<br/>
&ensp;ビルド: **101.71.18**<br/>
&ensp;リリース バージョン: **20.122052.17118.0**<br/>

**新機能**

- `mdatp connectivity test` は、製品が正しく機能するために必要な追加の URL で拡張されました。 新しい URL は [https://go.microsoft.com/fwlink/?linkid=2144709](https://go.microsoft.com/fwlink/?linkid=2144709).
- これまで、製品の再起動の間、製品ログ レベルは保持されませんでした。 このバージョン以降、ログ レベルを保持する新しいコマンド ライン ツール スイッチがあります。 新しいコマンドは .`mdatp log level persist --level <level>`
- まれに更新中に製品の状態が失われる可能性がある製品インストール パッケージのバグを修正しました
- ファイル コピー操作と組み込みの macOS アプリケーションのパフォーマンスの向上
- バグ修正

<br/>
</details>

<details>
  <summary>2022 年 6 月 (ビルド: 101.70.19 |リリース バージョン: 20.122051.17019.0)</summary>

&ensp;リリース **日: 2022 年 6 月 14** 日<br/>
&ensp;発行日: **2022 年 6 月 14** 日<br/>
&ensp;ビルド: **101.70.19**<br/>
&ensp;リリース バージョン: **20.122051.17019.0**<br/>

**新機能**

- 脅威関連の通知がエンド ユーザーに常に表示されないバグを修正しました。
- その他のバグ修正&パフォーマンスの向上

<br/>
</details>


<details>
  <summary>2022 年 6 月 (ビルド: 101.70.18 |リリース バージョン: 20.122042.17018.0)</summary>

&ensp;リリース **日: 2022 年 6 月 2** 日<br/>
&ensp;発行日: **2022 年 6 月 2 日**<br/>
&ensp;ビルド: **101.70.18**<br/>
&ensp;リリース バージョン: **20.122042.17018.0**<br/>

**新機能**

- 製品の更新中にインストール パッケージが無期限にハングすることがあるバグを修正しました
- 製品が検疫フォルダー内のファイルを誤って検出する場合があるバグを修正しました
- その他のバグ修正&パフォーマンスの向上

<br/>
</details>

<details>
  <summary>2022 年 5 月 (ビルド: 101.66.54 |リリース バージョン: 20.122041.16654.0) </summary>

&ensp;リリース日: **2022 年 5 月 11** 日<br/>
&ensp;発行日: **2022 年 5 月 11** 日<br/>
&ensp;ビルド: **101.66.54**<br/>
&ensp;リリース バージョン: **20.122041.16654.0**<br/>


**新機能**

- 場合によっては、正しいプロセス パスが印刷されない問題 `mdatp diagnostic real-time-protection-statistics` に対処しました。
- バグ修正

<br/>
</details>

<details>
  <summary>2022 年 4 月 (ビルド: 101.64.15 |リリース バージョン: 20.122032.16415.0)</summary>

&ensp;リリース日: **2022 年 4 月 26** 日<br/>
&ensp;発行日: **2022 年 4 月 26** 日<br/>
&ensp;ビルド: **101.64.15**<br/>
&ensp;リリース バージョン: **20.122032.16415.0**<br/>

**新機能**

- バージョン 101.61.69 で導入された回帰を修正しました。エンド ユーザーからの操作は必要ありませんでしたが、ステータス メニュー アイコンにエラー アイコンが表示される場合がありました
- フィールド`mdatp health`を`conflicting_applications`改善し、最新の 10 個のプロセスのみを表示し、プロセス名を含める必要があります。 これにより、Mac のMicrosoft Defender for Endpointと競合する可能性があるプロセスを簡単に特定できます。
- ベンダー ID と製品 ID が 16 進数ではなく 10 進数として表示されるバグ `mdatp device-control removable-media policy list` を修正しました
- その他のバグ修正&パフォーマンスの向上

<br/>
</details>

<details>
  <summary>Mar-2022 (ビルド: 101.61.69 |リリース バージョン: 20.122022.16169.0) </summary>

&ensp;リリース日: **2022 年 3 月 25** 日<br/>
&ensp;発行日: **2022 年 3 月 25** 日<br/>
&ensp;ビルド: **101.61.69**<br/>
&ensp;リリース バージョン: **20.122022.16169.0**<br/>

**新機能**

- バグ修正

<br/>
</details>

<details>
  <summary>Mar-2022 (ビルド: 101.60.91 |リリース バージョン: 20.122021.16091.0)</summary>

&ensp;リリース日: **2022 年 3 月 8** 日<br/>
&ensp;発行日: **2022 年 3 月 8** 日<br/>
&ensp;ビルド: **101.60.91**<br/>
&ensp;リリース バージョン: **20.122021.16091.0**<br/>

**新機能**

- このバージョンには[、CVE-2022-23278](https://msrc-blog.microsoft.com/2022/03/08/guidance-for-cve-2022-23278-spoofing-in-microsoft-defender-for-endpoint/) のセキュリティ更新プログラムが含まれています

<br/>
</details>

<details>
  <summary>2022 年 2 月 (ビルド: 101.59.50 |リリース バージョン: 20.122021.15950.0) </summary>

&ensp;リリース **日: 2022 年 2 月 28** 日<br/>
&ensp;発行日: **2022 年 2 月 28** 日<br/>
&ensp;ビルド: **101.59.50**<br/>
&ensp;リリース バージョン: **20.122021.15950.0**<br/>

**新機能**

- このバージョンでは、macOS 12.3 のサポートが追加されます。 macOS 12.3 以降、 [Apple は Python 2.7 を削除しています](https://developer.apple.com/documentation/macos-release-notes/macos-12_3-release-notes)。 既定では、macOS には Python バージョンがプレインストールされません。 **必要なアクション**: 
  - ユーザーは、デバイスを macOS Marketplace 12.3 (またはそれ以降) に更新する前に、Mac のMicrosoft Defender for Endpointをバージョン 101.59.50 (またはそれ以降) に更新する必要があります。 この最小バージョン 101.59.50 は、macOS の弔弔上の Mac のMicrosoft Defender for Endpointに関する Python 関連の問題を解消するための前提条件です。
  - リモート展開の場合は、既存の MDM セットアップを Mac バージョン 101.59.50 (またはそれ以降) のMicrosoft Defender for Endpointに更新する必要があります。 MDM 経由で Mac バージョン用の古いMicrosoft Defender for Endpointを macOS Marketplace 12.3 (またはそれ以降) にプッシュすると、インストールエラーが発生します。

<br/>
</details>

<details>
  <summary>2022 年 2 月 (ビルド: 101.59.10 |リリース バージョン: 20.122012.15910.0)</summary>

&ensp;リリース **日: 2022 年 2 月 22** 日<br/>
&ensp;発行日: **2022 年 2 月 22** 日<br/>
&ensp;ビルド: **101.59.10**<br/>
&ensp;リリース バージョン: **20.122012.15910.0**<br/>

**新機能**

- コマンド ライン ツールでは、検疫されたファイルを、ファイルが最初に検出された場所以外の場所に復元できるようになりました。 これは 、 `mdatp threat quarantine restore --id [threat-id] --path [destination-folder]`.
- Thunderbolt 3 経由で接続されたデバイスを処理するための拡張デバイス制御
- 無効なベンダー ID と製品 ID を含むデバイス制御ポリシーの処理が改善されました。 このバージョンより前のバージョンでは、ポリシーに 1 つ以上の無効な ID が含まれていた場合、ポリシー全体が無視されました。 このバージョン以降では、ポリシーの無効な部分のみが無視されます。 ポリシーに関する問題は、次の手順で `mdatp device-control removable-media policy list`示されています。
- バグ修正

<br/>
</details>

<details>
  <summary>2022 年 2 月 (ビルド: 101.56.62 |リリース バージョン: 20.121122.15662.0)</summary>

&ensp;リリース **日: 2022 年 2 月 7** 日<br/>
&ensp;発行日: **2022 年 2 月 7** 日<br/>
&ensp;ビルド: **101.56.62**<br/>
&ensp;リリース バージョン: **20.121122.15662.0**<br/>

**新機能**

- バグ修正 

<br/>
</details>

<details>
  <summary> 2022 年 1 月 (ビルド: 101.56.35 |リリース バージョン: 20.121121.15635.0)</summary>

&ensp;リリース日: **2022 年 1 月 30** 日<br/>
&ensp;発行日: **2022 年 1 月 30** 日<br/>
&ensp;ビルド: **101.56.35**<br/>
&ensp;リリース バージョン: **20.121121.15635.0**<br/>

**新機能**

- アプリケーションの名前が "Microsoft Defender ATP" から "Microsoft Defender" に変更されました。 エンド ユーザーは、次の変更を確認します。
- アプリケーションのインストール パスが変更`/Application/Microsoft Defender ATP.app``/Applications/Microsoft Defender.app`されました。
- ユーザー エクスペリエンス内で、"Microsoft Defender ATP" の出現は "Microsoft Defender" に置き換えられています
- Mac 用のMicrosoft Defender for Endpointで配布されているネットワーク コンテンツ フィルターが原因で、一部の VPN アプリケーションが接続できない問題を解決しました
- 特定の特性を持つパッケージのインストールを妨げるオペレーティング システム (OS) の変更により、インストール パッケージを開けなかった macOS 12.2 ベータ 2 で検出された問題に対処しました。 この OS の変更は macOS 12.2 の最終リリースには含まれていないようですが、今後の macOS バージョンで再導入される可能性があります。 そのため、すべてのエンタープライズ管理者は、管理コンソールでMicrosoft Defender for Endpoint パッケージをこの製品バージョン (または新しいバージョン) に更新することをお勧めします。
- 一部の M1 デバイスで、製品が無効なマルウェア対策定義でスタックし、ワーキング セットの定義に正常に更新できなかった問題に対処しました。
- `mdatp health`出力は、Mac 用のMicrosoft Defender for Endpointのすべてのコンポーネントにフル ディスク アクセスが許可されているかどうかを判断するために使用できる追加の属性`full_disk_access_enabled`を使用して拡張されました。
- バグ修正&パフォーマンスの向上

<br/>
</details>

<details>
  <summary>2022 年 1 月 (ビルド: 101.54.16 |リリース バージョン: 20.121111.15416.0) </summary>

&ensp;リリース日: **2022 年 1 月 12** 日<br/>
&ensp;発行日: **2022 年 1 月 12** 日<br/>
&ensp;ビルド: **101.54.16**<br/>
&ensp;リリース バージョン: **20.121111.15416.0**<br/>

**新機能**

- macOS 10.14 (Mojave) はサポートされなくなりました
- MDM を使用して管理者が製品設定の管理を停止すると、管理される前の値に戻ります (エンド ユーザーによってローカルに構成された値、またはそのようなローカル値が明示的に指定されていない場合は、製品によって使用される既定値)。 この変更の前に、設定の管理が停止した後、その管理値は保持され、製品によって引き続き使用されていました。
- バグ修正&パフォーマンスの向上
    
<br/>
</details>

<details><summary>2021 リリース </summary><blockquote>
    <details><summary>(ビルド: 101.49.25 |リリース バージョン: 20.121092.14925.0)</summary>

&ensp;ビルド: **101.49.25**<br/>
&ensp;リリース バージョン: **20.121092.14925.0** <br/>

**新機能**

- オンデマンド スキャン中にアーカイブをスキャンするかどうかを制御する新しいスイッチをコマンド ライン ツールに追加しました。 これを使用して `mdatp config scan-archives --value [enabled/disabled]`構成できます。 既定では、これは有効に設定されています。 
- バグ修正  

<br/>
</details>
 
<details><summary>(ビルド: 101.47.27 |リリース バージョン: 20.121082.14727.0)</summary>

&ensp;ビルド: **101.47.27**<br/>
&ensp;リリース バージョン: **20.121082.14727.0** <br/>

**新機能**
- macOS Mojave と macOS Catalina のシャットダウン時に発生するシステムのフリーズを修正しました。 

<br/>
</details>

<details><summary>(ビルド: 101.43.84 |リリース バージョン: 20.121082.14384.0)</summary>

&ensp;ビルド: **101.43.84**<br/>
&ensp;リリース バージョン: **20.121082.14384.0** <br/>

**新機能**
- macOS 12 の候補ビルド (Parse) 
- バグ修正 

<br/>
</details>

<details><summary>(ビルド: 101.41.10 |リリース バージョン: 20.121072.14110.0)</summary>

&ensp;ビルド: **101.41.10**<br/>
&ensp;リリース バージョン: **20.121072.14110.0** <br/>

**新機能**
- コマンド ライン ツールに新しいスイッチを追加しました。 
    - オンデマンド スキャンの並列処理の度合いを制御します。 これを使用して `mdatp config maximum-on-demand-scan-threads --value [number-between-1-and-64]`構成できます。 既定では、2 の並列処理の度合いが使用されます。 
    - セキュリティ インテリジェンスの更新後のスキャンを有効または無効にするかどうかを制御します。 これを使用して `mdatp config scan-after-definition-update --value [enabled/disabled]`構成できます。 既定では、これは有効に設定されています。 
- 製品ログ レベルを変更するには、昇格が必要になりました。 
- バグ修正&パフォーマンスの向上 

<br/>
</details>

<details><summary>(ビルド: 101.40.84 |リリース バージョン: 20.121071.14084.0)</summary>

&ensp;ビルド: **101.40.84**<br/>
&ensp;リリース バージョン: **20.121071.14084.0** <br/>

**新機能**
- M1 チップネイティブサポート 
- バグ修正&パフォーマンスの向上 

<br/>
</details>

<details><summary>(ビルド: 101.37.97 |リリース バージョン: 20.121062.13797.0)</summary>

&ensp;ビルド: **101.37.97**<br/>
&ensp;リリース バージョン: **20.121062.13797.0** <br/>

**新機能**
- バグ修正&パフォーマンスの向上 

<br/>
</details>

<details><summary>(ビルド: 101.34.28 |リリース バージョン: 20.121061.13428.0)</summary>

&ensp;ビルド: **101.34.28**<br/>
&ensp;リリース バージョン: **20.121061.13428.0** <br/>

**新機能**
- バグ修正 

<br/>
</details>

<details><summary>(ビルド: 101.34.27 |リリース バージョン: 20.121052.13427.0)</summary>

&ensp;ビルド: **101.34.27**<br/>
&ensp;リリース バージョン: **20.121052.13427.0** <br/>

**新機能**
- バグ修正 

<br/>
</details>

<details><summary>(ビルド: 101.34.20 |リリース バージョン: 20.121051.13420.0)</summary>

&ensp;ビルド: **101.34.20**<br/>
&ensp;リリース バージョン: **20.121051.13420.0** <br/>

**新機能**
- [macOS](mac-device-control-overview.md)  のデバイス制御は一般公開されています。 
- macOS 11 (Big Sur) の状態メニューからクイック スキャンを開始できない問題に対処しました。 
- その他のバグ修正 

<br/>
</details>

<details><summary>(ビルド: 101.32.69 |リリース バージョン: 20.121042.13269.0)</summary>

&ensp;ビルド: **101.32.69**<br/>
&ensp;リリース バージョン: **20.121042.13269.0** <br/>

**新機能**
- Microsoft Defender for Endpointやその他のアプリケーションからキーチェーンに同時にアクセスすると、キーチェーンが破損する可能性がある問題に対処しました。

<br/>
</details>

<details><summary>(ビルド: 101.29.64 |リリース バージョン: 20.121042.12964.0)</summary>

&ensp;ビルド: **101.29.64**<br/>
&ensp;リリース バージョン: **20.121042.12964.0** <br/> 

**新機能**
- このバージョン以降、コマンド ライン クライアントを介してトリガーされたオンデマンドウイルス対策スキャン中に検出された脅威は自動的に修復されます。 ユーザー インターフェイスを介してトリガーされたスキャン中に検出された脅威には、手動操作が必要です。 
- `mdatp diagnostic real-time-protection-statistics` 次の 2 つの追加スイッチがサポートされるようになりました。 
    - `--sort`: 出力を降順に並べ替え、スキャンされたファイルの合計数で並べ替えます。 
    - `--top N`: 上位 N 個の結果が表示されます (指定されている場合 `--sort` にのみ機能します) 
- パフォーマンスの向上 (特に `YARN` 使用時) &バグ修正

<br/>
</details>

<details><summary>(ビルド: 101.27.50 |リリース バージョン: 20.121022.12750.0)</summary>

&ensp;ビルド: **101.27.50**<br/>
&ensp;リリース バージョン: **20.121022.12750.0** <br/> 

**新機能**
- macOS Catalina 以前の Apple 証明書の有効期限に対応するように修正しました。 この修正プログラムは、脅威&脆弱性管理 (TVM) 機能を復元します。  

<br/>
</details>

<details><summary>(ビルド: 101.25.69 |リリース バージョン: 20.121022.12569.0)</summary>

&ensp;ビルド: **101.25.69**<br/>
&ensp;リリース バージョン: **20.121022.12569.0** <br/> 

**新機能**
- macOS のMicrosoft Defender for Endpointは、米国政府機関のお客様向けにプレビューで利用できるようになりました。 詳細については、「 [米国政府機関のお客様向けのMicrosoft Defender for Endpoint](gov.md)」を参照してください。 
- パフォーマンスの向上 (特に XCode シミュレーター アプリが使用されている場合) &バグ修正が行われました。 

<br/>
</details>

<details><summary>(ビルド: 101.23.64 |リリース バージョン: 20.121021.12364.0)</summary>

&ensp;ビルド: **101.23.64**<br/>
&ensp;リリース バージョン: **20.121021.12364.0** <br/> 

**新機能**
- 最後のオンデマンド スキャンに関する情報を表示する新しいオプションをコマンド ライン ツールに追加しました。 最後のオンデマンド スキャンに関する情報を表示するには、実行 `mdatp health --details antivirus`します。 
- バグ修正&パフォーマンスの向上 

<br/>
</details>

</details>

<details><summary>以前のリリース </summary><blockquote>
<details><summary>(ビルド: 101.22.79 |リリース バージョン: 20.121012.12279.0)</summary>

&ensp;ビルド: **101.22.79** <br> &ensp;リリース バージョン: **20.121012.12279.0**<br>

**新機能**
- バグ修正&パフォーマンスの向上 

<br/>
</details>

<details><summary>(ビルド: 101.19.88 |リリース バージョン: 20.121011.11988.0)</summary>

&ensp;ビルド:**101.19.88**<br>
&ensp;リリース バージョン: **20.121011.11988.0**<br>

**新機能**
- バグ修正&パフォーマンスの向上 

<br/>
</details>

<details><summary>(ビルド: 101.19.48 |リリース バージョン: 20.120121.11948.0)</summary>

&ensp;ビルド: **101.19.48**<br>
&ensp;リリース バージョン: **20.120121.11948.0**<br>

**新機能**
> [!NOTE]
> このリリースでは、古いコマンド ライン ツール構文は非推奨になりました。 新しい構文の詳細については、「リソース」を参照 [してください](mac-resources.md#configuring-from-the-command-line)。 
- ネットワーク拡張機能を無効にする新しいコマンド ライン スイッチを追加しました `mdatp system-extension network-filter disable`。 このコマンドは、Mac でのMicrosoft Defender for Endpointに関連するネットワークの問題のトラブルシューティングに役立ちます。 
- バグ修正&パフォーマンスの向上 

<br/>
</details>

<details><summary>(ビルド: 101.19.21 |リリース バージョン: 20.120101.11921.0)</summary>

&ensp;ビルド: **101.19.21**<br>
&ensp;リリース バージョン: **20.120101.11921.0** <br>

**新機能**
- バグ修正 

<br/>
</details>

<details><summary>(ビルド: 101.15.26 |リリース バージョン: 20.120102.11526.0)</summary>

&ensp;ビルド: **101.15.26**<br>
&ensp;リリース バージョン: **20.120102.11526.0**<br>

**新機能**
- macOS 11 Big Sur で実行するときのエージェントの信頼性が向上しました。 
- カスタム スキャン () 中に AV 除外を無視する新しいコマンド ライン スイッチ (`--ignore-exclusions``mdatp scan custom`) を追加しました。 
- バグ修正&パフォーマンスの向上

<br/> 
</details>

<details><summary>(ビルド: 101.13.75 |リリース バージョン: 20.120101.11375.0)</summary>

&ensp;ビルド: **101.13.75**<br>
&ensp;リリース バージョン: **20.120101.11375.0**<br>

**新機能** 
- Microsoft Defender for Endpointがカーネル パニックに陥る macOS 11 (Big Sur) バグをトリガーしていた場合の条件を削除しました。 
- Mac 11 (Big Sur) で実行されている Endpoint Security システム拡張機能のメモリ リークを修正しました。 
- バグ修正 

<br/>
</details>

<details><summary>(ビルド: 101.10.72)</summary>

&ensp;ビルド: **101.10.72** <br>

**新機能** 
- バグ修正  

<br/>
</details>

<details><summary>(ビルド: 101.09.61)</summary>

&ensp;ビルド: **101.09.61**<br>

**新機能** 
-  [フィードバックを送信するオプションを無効にするための](mac-preferences.md#show--hide-option-to-send-feedback)新しい管理設定を追加しました。 
- 製品の設定が管理されているときに、[状態] メニュー アイコンに正常な状態が表示されるようになりました。 以前は、製品設定が管理者によって管理されていたにもかかわらず、状態メニュー アイコンに警告またはエラーの状態が表示されていました。 
- バグ修正&パフォーマンスの向上 

<br/>
</details>

<details><summary>(ビルド: 101.09.50)</summary>

&ensp;ビルド: **101.09.50**<br>

**新機能** 
- この製品バージョンは、macOS Big Sur 11 beta 9 で検証されています。 
- mdatp コマンド ライン ツールの新しい構文が既定の構文になりました。 新しい構文の詳細については、 [macOS でのMicrosoft Defender for Endpointのリソースに関するページを](mac-resources.md#configuring-from-the-command-line)参照してください。 
> [!NOTE]
> 古いコマンド ライン ツール構文は **、2021 年 1 月 1 日** に製品から削除されます。
- 診断ログを別のディレクトリに保存できるようにする新しいパラメーター (`--path [directory]`) を使用して拡張されました。 `mdatp diagnostic create`  
- バグ修正&パフォーマンスの向上 

<br/>
</details>

<details><summary>(ビルド: 101.09.49)</summary>

&ensp;ビルド: **101.09.49**<br>

**新機能** 
- IT 管理者によって管理される除外と、ローカル ユーザーによって定義された除外を区別するためのユーザー インターフェイスの機能強化。 
- オンデマンド スキャン中の CPU 使用率が向上しました。 
- バグ修正&パフォーマンスの向上 

<br/>
</details>

<details><summary>(ビルド: 101.07.23)</summary>

&ensp;ビルド: **101.07.23**<br>

**新機能** 
- パッシブ モードの `mdatp --health` 状態と EDR グループ ID を確認するための新しいフィールドを出力に追加しました。 
> [!NOTE]
> `mdatp --health` は、今後の `mdatp health` 製品更新プログラムで置き換えられます。 
- ユーザー インターフェイスで自動サンプル送信がマネージドとしてマークされていないバグを修正しました。 
- ウイルス対策スキャン履歴内のアイテムの保持を制御するための新しい設定を追加しました。  [スキャン履歴内のアイテムを保持する日数を指定し、スキャン履歴](mac-preferences.md#antivirus-scan-history-retention-in-days)  [内のアイテムの最大数を指定](mac-preferences.md#maximum-number-of-items-in-the-antivirus-scan-history)できるようになりました。 
- バグ修正 

<br/>
</details>

<details><summary>(ビルド: 101.06.63)</summary>

&ensp;ビルド: **101.06.63**<br>

**新機能** 
- バージョン `101.05.17`で導入されたパフォーマンス低下に対処しました。 この回帰は、SMB 共有にアクセスするときに一部のお客様が観察したカーネル パニックを解消するための修正プログラムで導入されました。 このコード変更を元に戻し、カーネル パニックを解消する別の方法を調査しています。 

<br/>
</details>

<details><summary>(ビルド: 101.05.17)</summary>

&ensp;ビルド: **101.05.17**<br> 

**新機能** 
> [!IMPORTANT]
> コマンド ライン ツールの新しい拡張構文に取り `mdatp` 組んでいます。 現在、新しい構文は Insider Fast および Insider スロー更新チャネルの既定値です。 この新しい構文を使用して、自分自身を偽装することをお勧めします。 新しい構文と並行して古い構文を引き続きサポートし、今後数か月の間に古い構文の非推奨計画に関するより多くのコミュニケーションを提供します。 
- SMB ファイル共有にアクセスするときに発生するカーネル パニックに対処しました。 
- バグ修正&パフォーマンスの向上 

<br/>
</details>

<details><summary>(ビルド: 101.05.16)</summary>

&ensp;ビルド: **101.05.16**<br>

**新機能** 
- スキャンされたファイルの数を大幅に減らすクイック スキャン ロジックの機能強化。 
- コマンド ライン ツールの [オートコンプリートのサポート](mac-resources.md#how-to-enable-autocompletion) を追加しました。 
- バグ修正 

<br/>
</details>

<details><summary>(ビルド: 101.03.12)</summary>

&ensp;ビルド: **101.03.12**<br>

**新機能** 
- バグ修正&パフォーマンスの向上 

<br/>
</details>

<details><summary>(ビルド: 101.01.54)</summary>

&ensp;ビルド: **101.01.54**<br>

**新機能** 
- Time Machine との互換性に関する機能強化 
- アクセシビリティの改善点 
- バグ修正&パフォーマンスの向上 

<br/>
</details>

<details><summary>(ビルド: 101.00.31)</summary>

&ensp;ビルド: **101.00.31** <br>

**新機能** 
-  [Intune ユーザー向けの製品オンボード エクスペリエンスの](/mem/intune/apps/apps-advanced-threat-protection-macos)向上 
- ウイルス対策 [の除外でワイルドカードがサポートされるようになりました](mac-exclusions.md#supported-exclusion-types)
- macOS コンテキスト メニューからウイルス対策スキャンをトリガーする機能を追加しました。 Finder でファイルまたはフォルダーを右クリックし、 **Microsoft Defender for Endpointでスキャン** を選択できるようになりました。 
- インプレース製品のダウングレードは、インストーラーによって明示的に禁止されるようになりました。 ダウングレードする必要がある場合は、まず既存のバージョンをアンインストールし、デバイスを再構成します。 
- バグ修正&その他のパフォーマンスの向上 

<br/>
</details>

<details><summary>(ビルド: 100.90.27)</summary>

&ensp;ビルド: **100.90.27** <br>   

**新機能** 
- macOS では、システム全体の [更新チャネル](mac-updates.md#set-the-channel-name) とは異なるMicrosoft Defender for Endpointの更新チャネルを設定できるようになりました。 
- 新しい製品アイコン 
- その他のユーザー エクスペリエンスの改善 
- バグ修正 

<br/>
</details>

<details><summary>(ビルド: 100.86.92)</summary>

&ensp;ビルド: **100.86.92**<br>

**新機能** 
- Time Machine との互換性に関する機能強化 
- アンインストール中に製品がすべてのファイルをクリーニングしないことがある問題に `/Library/Application Support/Microsoft/Defender` 対処しました。 
- Microsoft AutoUpdate を使用して Microsoft 製品が更新されたときに、製品の CPU 使用率が低下しました。 
- バグ修正&その他のパフォーマンスの向上 

<br/>
</details>

<details><summary>(ビルド: 100.86.91)</summary>

&ensp;ビルド: **100.86.91**<br>

**新機能**
> [!CAUTION]
> macOS デバイスの最も完全な保護を確保し、Apple が [current - 2] より前の OS バージョンへの macOS ネイティブ セキュリティ更新プログラムの配信を停止することに合わせて、MDATP for Mac の展開と更新は、macOS Sierra [10.12] ではサポートされなくなります。 MDATP for Mac の更新と機能強化は、Catalina [10.15]、Mojave [10.14]、High Sierra [10.13] を実行しているデバイスに配信されます。
>
> Sierra [10.12] デバイスに MDATP for Mac が既に展開されている場合は、保護を失うリスクを排除するために、最新の macOS バージョンにアップグレードしてください。

-  バグ修正&パフォーマンスの向上 

<br/>
</details>

<details><summary>(ビルド: 100.83.73)</summary>

&ensp;ビルド: **100.83.73**<br>

**新機能**
- 除外の管理、 [脅威の種類の設定](mac-preferences.md#threat-type-settings-merge-policy) [の管理](mac-preferences.md#exclusion-merge-policy)、 [および許可されていない脅威アクション](mac-preferences.md#disallowed-threat-actions)に関する IT 管理者向けのコントロールが追加されました。 
- デバイスでフル ディスク アクセスが有効になっていない場合、状態メニューに警告が表示されるようになりました。 
- バグ修正&パフォーマンスの向上
 
<br/>
</details>

<details><summary>(ビルド: 100.82.60)</summary>

&ensp;ビルド: **100.82.60** <br>

**新機能**
- 定義の更新後に製品が起動できない問題に対処しました。

<br/> 
</details>

<details><summary>(ビルド: 100.80.42)</summary>

&ensp;ビルド: **100.80.42**<br>

**新機能**
- バグ修正

<br/> 
</details>

<details><summary>(ビルド: 100.79.42)</summary>

&ensp;ビルド: **100.79.42**<br>

**新機能**
- Mac のMicrosoft Defender for Endpointが Time Machine に干渉する場合がある問題を修正しました。 
- バックエンド サービスとの接続をテストするための新しいスイッチをコマンド ライン ユーティリティに追加しました
 
  ```bash
  mdatp connectivity test
  ```
- ユーザー インターフェイスで完全な脅威履歴を表示する機能を追加しました ( **保護履歴** ビューからアクセスできます)。 
- バグ修正&パフォーマンスの向上

<br/>
</details>

<details><summary>(ビルド: 100.72.15)</summary> 

&ensp;ビルド: **100.72.15**<br>

**新機能**
- バグ修正 

<br/>
</details>

<details><summary>(ビルド: 100.70.99)</summary> 

&ensp;ビルド: **100.70.99**<br>

**新機能**
- リアルタイム保護が有効になっている場合に、一部のユーザーが macOS Catalina にアップグレードする機能に影響する問題に対処しました。 この散発的な問題は、Catalina アップグレード パッケージ内のファイルをMicrosoft Defender for Endpointロックしながら脅威をスキャンしたことが原因で発生し、アップグレード シーケンスでエラーが発生しました。

<br/>
</details> 

<details><summary>(ビルド: 100.68.99)</summary> 

&ensp;ビルド: **100.68.99**<br>

**新機能**
-  [パッシブ モード](mac-preferences.md#enforcement-level-for-antivirus-engine)で実行するようにウイルス対策機能を構成する機能を追加しました。 
- バグ修正&パフォーマンスの向上 

<br/>
</details>

<details><summary>(ビルド: 100.65.28)</summary> 

&ensp;ビルド: **100.65.28**<br>

**新機能**
- macOS Catalina のサポートが追加されました。 
> [!CAUTION]
> macOS 10.15 (Catalina) には、新しいセキュリティとプライバシーの強化が含まれています。 このバージョン以降、既定では、アプリケーションは明示的な同意なしにディスク上の特定の場所 (ドキュメント、ダウンロード、デスクトップなど) にアクセスできません。 この同意がない場合、Microsoft Defender for Endpointはデバイスを完全に保護できません。
> 
> この同意を付与するメカニズムは、Microsoft Defender for Endpointのデプロイ方法によって異なります。
> 
> - 手動デプロイについては、「手動デプロイ」 [トピック](mac-install-manually.md#how-to-allow-full-disk-access)の更新された手順を参照してください。
> - マネージド デプロイについては、 [JAMF ベースのデプロイ](mac-install-with-jamf.md)とMicrosoft Intune ベースの [デプロイ](mac-install-with-intune.md#create-system-configuration-profiles) に関するトピックで更新された手順を参照してください。 

- バグ修正&パフォーマンスの向上 

<br/>
</details>

<br/><br/>
</details>