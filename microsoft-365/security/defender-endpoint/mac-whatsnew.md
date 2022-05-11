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
ms.openlocfilehash: ec545bb38456b778b627c41994a1eb18ae665a86
ms.sourcegitcommit: 2d870e06e87b10d9e8ec7a7a8381353bc3bc59c7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2022
ms.locfileid: "65349756"
---
# <a name="whats-new-in-microsoft-defender-for-endpoint-on-mac"></a>Mac でのMicrosoft Defender for Endpointの新機能

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

## <a name="1016654-20122041166540"></a>101.66.54 (20.122041.16654.0)

- 場合によっては、正しいプロセス パスが印刷されない問題 `mdatp diagnostic real-time-protection-statistics` に対処しました。
- バグ修正

## <a name="1016415-20122032164150"></a>101.64.15 (20.122032.16415.0)

- バージョン 101.61.69 で導入された回帰を修正しました。エンド ユーザーからの操作は必要ありませんでしたが、ステータス メニュー アイコンにエラー アイコンが表示される場合がありました
- フィールド`mdatp health`を`conflicting_applications`改善し、最新の 10 個のプロセスのみを表示し、プロセス名を含める必要があります。 これにより、Mac のMicrosoft Defender for Endpointと競合する可能性があるプロセスを簡単に特定できます。
- ベンダー ID と製品 ID が 16 進数ではなく 10 進数として表示されるバグ `mdatp device-control removable-media policy list` を修正しました
- その他のバグ修正&パフォーマンスの向上

## <a name="1016169-20122022161690"></a>101.61.69 (20.122022.16169.0)

- バグ修正

## <a name="1016091-20122021160910"></a>101.60.91 (20.122021.16091.0)

- このバージョンには[、CVE-2022-23278](https://msrc-blog.microsoft.com/2022/03/08/guidance-for-cve-2022-23278-spoofing-in-microsoft-defender-for-endpoint/) のセキュリティ更新プログラムが含まれています

## <a name="1015950-20122021159500"></a>101.59.50 (20.122021.15950.0)

- このバージョンでは、macOS 12.3 のサポートが追加されます。 macOS 12.3 以降、[Apple は Python 2.7 を削除しています](https://developer.apple.com/documentation/macos-release-notes/macos-12_3-release-notes)。 既定では、macOSには Python バージョンがプレインストールされません。 **必要なアクション**: 
  - ユーザーは、デバイスを MacOS の 12.3 (またはそれ以降) に更新する前に、Mac のMicrosoft Defender for Endpointをバージョン 101.59.50 (またはそれ以降) に更新する必要があります。 この最小バージョン 101.59.50 は、MacOSのMicrosoft Defender for Endpoint for Mac に関する Python 関連の問題を解消するための前提条件です。
  - リモート展開の場合は、既存の MDM セットアップを Mac バージョン 101.59.50 (またはそれ以降) のMicrosoft Defender for Endpointに更新する必要があります。 MDM 経由で Mac バージョンの古いMicrosoft Defender for Endpointを MacOS MacOSの 12.3 (またはそれ以降) にプッシュすると、インストールエラーが発生します。

## <a name="1015910-20122012159100"></a>101.59.10 (20.122012.15910.0)

- コマンド ライン ツールでは、検疫されたファイルを、ファイルが最初に検出された場所以外の場所に復元できるようになりました。 これは 、 `mdatp threat quarantine restore --id [threat-id] --path [destination-folder]`.
- Thunderbolt 3 経由で接続されたデバイスを処理するための拡張デバイス制御
- 無効なベンダー ID と製品 ID を含むデバイス制御ポリシーの処理が改善されました。 このバージョンより前のバージョンでは、ポリシーに 1 つ以上の無効な ID が含まれていた場合、ポリシー全体が無視されました。 このバージョン以降では、ポリシーの無効な部分のみが無視されます。 ポリシーに関する問題は、次の手順で `mdatp device-control removable-media policy list`示されています。
- バグ修正

## <a name="1015662-20121122156620"></a>101.56.62 (20.121122.15662.0)

- バグ修正

## <a name="1015635-20121121156350"></a>101.56.35 (20.121121.15635.0)

- アプリケーションの名前が "Microsoft Defender ATP" から "Microsoft Defender" に変更されました。 エンド ユーザーは、次の変更を確認します。
  - アプリケーションのインストール パスが変更`/Application/Microsoft Defender ATP.app``/Applications/Microsoft Defender.app`されました。
  - ユーザー エクスペリエンス内で、"Microsoft Defender ATP" の出現は "Microsoft Defender" に置き換えられています
- Mac 用のMicrosoft Defender for Endpointで配布されているネットワーク コンテンツ フィルターが原因で、一部の VPN アプリケーションが接続できない問題を解決しました
- macOS 12.2 ベータ 2 で、特定の特性を持つパッケージのインストールを妨げるオペレーティング システム (OS) の変更によりインストール パッケージを開けられなかった問題に対処しました。 この OS の変更はmacOS 12.2 の最終リリースには含まれていないようですが、今後のmacOS バージョンで再導入される可能性があります。 そのため、すべてのエンタープライズ管理者は、管理コンソールでMicrosoft Defender for Endpoint パッケージをこの製品バージョン (または新しいバージョン) に更新することをお勧めします。
- 一部の M1 デバイスで、製品が無効なマルウェア対策定義でスタックし、ワーキング セットの定義に正常に更新できなかった問題に対処しました。
- `mdatp health`出力は、Mac 用のMicrosoft Defender for Endpointのすべてのコンポーネントにフル ディスク アクセスが許可されているかどうかを判断するために使用できる追加の属性`full_disk_access_enabled`を使用して拡張されました。
- バグ修正&パフォーマンスの向上

## <a name="1015416-20121111154160"></a>101.54.16 (20.121111.15416.0)

- macOS 10.14 (Mojave) はサポートされなくなりました
- MDM を使用して管理者が製品設定の管理を停止すると、管理される前の値に戻ります (エンド ユーザーによってローカルに構成された値、またはそのようなローカル値が明示的に指定されていない場合は、製品によって使用される既定値)。 この変更の前に、設定の管理が停止した後、その管理値は保持され、製品によって引き続き使用されていました。
- バグ修正&パフォーマンスの向上

## <a name="1014925-20121092149250"></a>101.49.25 (20.121092.14925.0)

- オンデマンド スキャン中にアーカイブをスキャンするかどうかを制御する新しいスイッチをコマンド ライン ツールに追加しました。 これを構成 `mdatp config scan-archives --value [enabled/disabled]`するには、 . 既定では、これは `enabled`.
- バグ修正

## <a name="1014727-20121082147270"></a>101.47.27 (20.121082.14727.0)

- macOS Mojave と macOS Catalina のシャットダウン時に発生するシステムのフリーズを修正しました

## <a name="1014384-20121082143840"></a>101.43.84 (20.121082.14384.0)

- macOS 12 の候補ビルド (12)
- バグ修正

## <a name="1014110-20121072141100"></a>101.41.10 (20.121072.14110.0)

- コマンド ライン ツールに新しいスイッチを追加しました。
  - オンデマンド スキャンの並列処理の度合いを制御します。 これを構成 `mdatp config maximum-on-demand-scan-threads --value [number-between-1-and-64]`するには、 . 既定では、ある程度の並列処理 `2` が使用されます。
  - セキュリティ インテリジェンスの更新後のスキャンを有効または無効にするかどうかを制御します。 これを構成 `mdatp config scan-after-definition-update --value [enabled/disabled]`するには、 . 既定では、これは `enabled`.
- 製品ログ レベルを変更するには、昇格が必要になりました
- バグ修正&パフォーマンスの向上

## <a name="1014084-20121071140840"></a>101.40.84 (20.121071.14084.0)

- M1 チップネイティブサポート
- バグ修正&パフォーマンスの向上

## <a name="1013797-20121062137970"></a>101.37.97 (20.121062.13797.0)

- バグ修正&パフォーマンスの向上

## <a name="1013428-20121061134280"></a>101.34.28 (20.121061.13428.0)

- バグ修正

## <a name="1013427-20121052134270"></a>101.34.27 (20.121052.13427.0)

- バグ修正

## <a name="1013420-20121051134200"></a>101.34.20 (20.121051.13420.0)

- [macOSのデバイス制御](mac-device-control-overview.md)が一般公開されるようになりました
- macOS 11 (Big Sur) の状態メニューからクイック スキャンを開始できない問題に対処しました
- その他のバグ修正

## <a name="1013269-20121042132690"></a>101.32.69 (20.121042.13269.0)

- Microsoft Defender for Endpointやその他のアプリケーションからキーチェーンに同時にアクセスすると、キーチェーンが破損する可能性がある問題に対処しました。

## <a name="1012964-20121042129640"></a>101.29.64 (20.121042.12964.0)

- このバージョン以降、コマンド ライン クライアントを介してトリガーされたオンデマンドウイルス対策スキャン中に検出された脅威は自動的に修復されます。 ユーザー インターフェイスを介してトリガーされたスキャン中に検出された脅威には、手動操作が必要です。
- `mdatp diagnostic real-time-protection-statistics` 次の 2 つの追加スイッチがサポートされるようになりました。
  - `--sort`: 出力を降順に並べ替え、スキャンされたファイルの合計数で並べ替えます。
  - `--top N`: 上位 N 個の結果が表示されます (指定されている場合 `--sort` にのみ機能します)
- パフォーマンスの向上 (特にYARNが使用される場合) &バグ修正

## <a name="1012750-20121022127500"></a>101.27.50 (20.121022.12750.0)

- MacOS Catalina 以前の Apple 証明書の有効期限に対応するように修正しました。 この修正プログラムは、脅威&脆弱性管理 (TVM) 機能を復元します。

## <a name="1012569-20121022125690"></a>101.25.69 (20.121022.12569.0)

- macOSのMicrosoft Defender for Endpointは、米国政府機関のお客様向けのプレビューで利用できるようになりました。 詳細については、「[米国政府機関のお客様向けのMicrosoft Defender for Endpoint」を参照してください](gov.md)。
- パフォーマンスの向上 (特に XCode シミュレーター アプリが使用されている場合) &バグ修正が行われました。

## <a name="1012364-20121021123640"></a>101.23.64 (20.121021.12364.0)

- 最後のオンデマンド スキャンに関する情報を表示する新しいオプションをコマンド ライン ツールに追加しました。 最後のオンデマンド スキャンに関する情報を表示するには、次のコマンドを実行します。 `mdatp health --details antivirus`
- バグ修正&パフォーマンスの向上

## <a name="1012279-20121012122790"></a>101.22.79 (20.121012.12279.0)

- バグ修正&パフォーマンスの向上

## <a name="1011988-20121011119880"></a>101.19.88 (20.121011.11988.0)

- バグ修正&パフォーマンスの向上

## <a name="1011948-20120121119480"></a>101.19.48 (20.120121.11948.0)

> [!NOTE]
> このリリースでは、古いコマンド ライン ツール構文は非推奨になりました。 新しい構文の詳細については、「リソース」を参照 [してください](mac-resources.md#configuring-from-the-command-line)。

- ネットワーク拡張機能 `mdatp system-extension network-filter disable`を無効にする新しいコマンド ライン スイッチを追加しました。 このコマンドは、Mac でのMicrosoft Defender for Endpointに関連するネットワークの問題のトラブルシューティングに役立ちます
- バグ修正&パフォーマンスの向上

## <a name="1011921-20120101119210"></a>101.19.21 (20.120101.11921.0)

- バグ修正

## <a name="1011526-20120102115260"></a>101.15.26 (20.120102.11526.0)

- macOS 11 Big Sur で実行するときのエージェントの信頼性が向上しました
- カスタム スキャン中に AV 除外を無視する新しいコマンド ライン スイッチ (`--ignore-exclusions`) を追加しました (`mdatp scan custom`)
- バグ修正&パフォーマンスの向上

## <a name="1011375-20120101113750"></a>101.13.75 (20.120101.11375.0)

- Microsoft Defender for Endpointがカーネル パニックに現れる macOS 11 (Big Sur) バグをトリガーしていた場合の条件を削除しました
- Mac 11 (Big Sur) で実行されている Endpoint Security システム拡張機能のメモリ リークを修正しました
- バグ修正

## <a name="1011072"></a>101.10.72

- バグ修正

## <a name="1010961"></a>101.09.61

- [フィードバックを送信するオプションを無効にする](mac-preferences.md#show--hide-option-to-send-feedback)新しい管理設定を追加しました
- 製品の設定が管理されているときに、[状態] メニュー アイコンに正常な状態が表示されるようになりました。 以前は、製品の設定が管理者によって管理されていたにもかかわらず、状態メニュー アイコンに警告またはエラーの状態が表示されていました
- バグ修正&パフォーマンスの向上

## <a name="1010950"></a>101.09.50

- この製品バージョンは、macOS Big Sur 11 beta 9 で検証されています

- コマンド ライン ツールの `mdatp` 新しい構文が既定の構文になりました。 新しい構文の詳細については、「[macOSのMicrosoft Defender for Endpointのリソース」を](mac-resources.md#configuring-from-the-command-line)参照してください。

  > [!NOTE]
  > 古いコマンド ライン ツール構文は **、2021 年 1 月 1 日** に製品から削除されます。

- `mdatp diagnostic create`診断ログを別のディレクトリに保存できるようにする新しいパラメーター (`--path [directory]`) で拡張
- バグ修正&パフォーマンスの向上

## <a name="1010949"></a>101.09.49

- IT 管理者によって管理される除外と、ローカル ユーザーによって定義された除外を区別するためのユーザー インターフェイスの機能強化
- オンデマンド スキャン中の CPU 使用率の向上
- バグ修正&パフォーマンスの向上

## <a name="1010723"></a>101.07.23

- パッシブ モードとEDR グループ ID の`mdatp --health`状態を確認するための新しいフィールドを出力に追加しました

  > [!NOTE]
  > `mdatp --health` は、今後の `mdatp health` 製品更新プログラムで置き換えられます。

- ユーザー インターフェイスで自動サンプル送信がマネージドとしてマークされていないバグを修正しました
- ウイルス対策スキャン履歴内のアイテムの保持を制御するための新しい設定を追加しました。 [スキャン履歴内のアイテムを保持する日数を指定し、スキャン履歴](mac-preferences.md#antivirus-scan-history-retention-in-days)[内のアイテムの最大数を指定](mac-preferences.md#maximum-number-of-items-in-the-antivirus-scan-history)できるようになりました
- バグ修正

## <a name="1010663"></a>101.06.63

- バージョン `101.05.17`で導入されたパフォーマンス低下に対処しました。 この回帰は、SMB 共有にアクセスするときに一部のお客様が観察したカーネル パニックを解消するための修正プログラムで導入されました。 このコード変更を元に戻し、カーネル パニックを解消する別の方法を調査しています。

## <a name="1010517"></a>101.05.17

> [!IMPORTANT]
> コマンド ライン ツールの新しい拡張構文に取り `mdatp` 組んでいます。 現在、新しい構文は Insider Fast および Insider スロー更新チャネルの既定値です。 この新しい構文を使用して、自分自身を偽装することをお勧めします。
>
> 新しい構文と並行して古い構文を引き続きサポートし、今後数か月の間に古い構文の非推奨計画に関するより多くのコミュニケーションを提供します。

- SMB ファイル共有にアクセスするときに発生するカーネル パニックに対処しました
- バグ修正&パフォーマンスの向上

## <a name="1010516"></a>101.05.16

- スキャンされたファイルの数を大幅に減らすクイック スキャン ロジックの機能強化
- コマンド ライン ツールの [オートコンプリートのサポート](mac-resources.md#how-to-enable-autocompletion) を追加しました
- バグ修正

## <a name="1010312"></a>101.03.12

- バグ修正&パフォーマンスの向上

## <a name="1010154"></a>101.01.54

- Time Machine との互換性に関する機能強化
- アクセシビリティの改善点
- バグ修正&パフォーマンスの向上

## <a name="1010031"></a>101.00.31

- [Intune ユーザー向けの製品オンボード エクスペリエンスの](/mem/intune/apps/apps-advanced-threat-protection-macos)向上
- ウイルス対策 [の除外でワイルドカードがサポートされるようになりました](mac-exclusions.md#supported-exclusion-types)
- macOSコンテキスト メニューからウイルス対策スキャンをトリガーする機能を追加しました。 Finder でファイルまたはフォルダーを右クリックし、[**スキャンと共にスキャン] を選択できるようになりましたMicrosoft Defender for Endpoint**
- インプレース製品のダウングレードは、インストーラーによって明示的に禁止されるようになりました。 ダウングレードする必要がある場合は、まず既存のバージョンをアンインストールし、デバイスを再構成します
- バグ修正&その他のパフォーマンスの向上

## <a name="1009027"></a>100.90.27

- システム全体[の更新チャネル](mac-updates.md#set-the-channel-name)とは異なるmacOSで、Microsoft Defender for Endpointの更新チャネルを設定できるようになりました
- 新しい製品アイコン
- その他のユーザー エクスペリエンスの改善
- バグ修正

## <a name="1008692"></a>100.86.92

- Time Machine との互換性に関する機能強化
- アンインストール中に製品がすべてのファイル `/Library/Application Support/Microsoft/Defender` をクリーニングしないことがある問題に対処しました
- Microsoft AutoUpdate を使用して Microsoft 製品が更新された場合の製品の CPU 使用率の低下
- バグ修正&その他のパフォーマンスの向上

## <a name="1008691"></a>100.86.91

> [!CAUTION]
> macOS デバイスの最も完全な保護を確保し、Apple が [current - 2] より古い OS バージョンへのmacOSネイティブ セキュリティ更新プログラムの配信を停止するために、MDATP for Mac の展開と更新プログラムはmacOS Sierra [10.12] ではサポートされなくなります。 MDATP for Mac の更新と機能強化は、Catalina [10.15]、Mojave [10.14]、High Sierra [10.13] を実行しているデバイスに配信されます。
>
> Sierra [10.12] デバイスに MDATP for Mac が既に展開されている場合は、保護を失うリスクを排除するために、最新のmacOS バージョンにアップグレードしてください。

- バグ修正&パフォーマンスの向上

## <a name="1008373"></a>100.83.73

- 除外の管理、[脅威の種類の設定](mac-preferences.md#threat-type-settings-merge-policy)[の管理](mac-preferences.md#exclusion-merge-policy)、[および許可されていない脅威アクション](mac-preferences.md#disallowed-threat-actions)に関する IT 管理者向けのコントロールが追加されました
- デバイスでフル ディスク アクセスが有効になっていない場合、状態メニューに警告が表示されるようになりました
- バグ修正&パフォーマンスの向上

## <a name="1008260"></a>100.82.60

- 定義の更新後に製品が起動できない問題に対処しました。

## <a name="1008042"></a>100.80.42

- バグ修正

## <a name="1007942"></a>100.79.42

- Mac のMicrosoft Defender for Endpointが Time Machine に干渉する場合がある問題を修正しました
- バックエンド サービスとの接続をテストするための新しいスイッチをコマンド ライン ユーティリティに追加しました

  ```bash
  mdatp connectivity test
  ```

- ユーザー インターフェイスで完全な脅威履歴を表示する機能を追加しました ( **保護履歴** ビューからアクセスできます)
- バグ修正&パフォーマンスの向上

## <a name="1007215"></a>100.72.15

- バグ修正

## <a name="1007099"></a>100.70.99

- リアルタイム保護が有効になっている場合に、一部のユーザーが macOS Catalina にアップグレードする機能に影響する問題に対処しました。 この散発的な問題は、Catalina アップグレード パッケージ内のファイルをMicrosoft Defender for Endpointロックしながら脅威をスキャンしたことが原因で発生し、アップグレード シーケンスでエラーが発生しました。

## <a name="1006899"></a>100.68.99

- [パッシブ モード](mac-preferences.md#enforcement-level-for-antivirus-engine)で実行するようにウイルス対策機能を構成する機能を追加しました
- バグ修正&パフォーマンスの向上

## <a name="1006528"></a>100.65.28

- macOS Catalina のサポートを追加しました

  > [!CAUTION]
  > macOS 10.15 (Catalina) には、新しいセキュリティとプライバシーの強化が含まれています。 このバージョン以降、既定では、アプリケーションは明示的な同意なしにディスク上の特定の場所 (ドキュメント、ダウンロード、デスクトップなど) にアクセスできません。 この同意がない場合、Microsoft Defender for Endpointはデバイスを完全に保護できません。
  >
  > この同意を付与するメカニズムは、Microsoft Defender for Endpointのデプロイ方法によって異なります。
  >
  > - 手動デプロイについては、「 [手動](mac-install-manually.md#how-to-allow-full-disk-access) デプロイ」トピックの更新された手順を参照してください。
  > - マネージド デプロイについては、[JAMF ベースのデプロイとMicrosoft Intune ベースのデプロイに関](mac-install-with-jamf.md)するトピックの[](mac-install-with-intune.md#create-system-configuration-profiles)更新された手順を参照してください。

- バグ修正&パフォーマンスの向上
