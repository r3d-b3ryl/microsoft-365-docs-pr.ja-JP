---
title: Microsoft Defender for Endpoint on Mac の新機能
description: 以前のバージョンの Microsoft Defender for Endpoint on Mac の主な変更点について説明します。
keywords: microsoft, defender, Microsoft Defender for Endpoint, mac, installation, macos, whatsnew
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
ms.openlocfilehash: d8b2c7725354facb01f8b12af502aae19856afe8
ms.sourcegitcommit: 3b8e009ea1ce928505b8fc3b8926021fb91155f3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2022
ms.locfileid: "64500741"
---
# <a name="whats-new-in-microsoft-defender-for-endpoint-on-mac"></a>Microsoft Defender for Endpoint on Mac の新機能

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

## <a name="1016169-20122022161690"></a>101.61.69 (20.122022.16169.0)

- バグ修正

## <a name="1016091-20122021160910"></a>101.60.91 (20.122021.16091.0)

- このバージョンには、 [CVE-2022-23278 のセキュリティ更新プログラムが含まれている](https://msrc-blog.microsoft.com/2022/03/08/guidance-for-cve-2022-23278-spoofing-in-microsoft-defender-for-endpoint/)

## <a name="1015950-20122021159500"></a>101.59.50 (20.122021.15950.0)

- このバージョンでは、macOS 12.3 のサポートが追加されます。 macOS 12.3 から [、Apple は Python 2.7 を削除しています](https://developer.apple.com/documentation/macos-release-notes/macos-12_3-release-notes)。 既定では、macOS に Python バージョンがプレインストールされません。 **必要なアクション**: 
  - ユーザーは、デバイスを macOS モントレー 12.3 (または新しい) に更新する前に、Microsoft Defender for Endpoint for Mac をバージョン 101.59.50 (以降) に更新する必要があります。 この最小限のバージョン 101.59.50 は、macOS モントレーの Microsoft Defender for Endpoint for Mac に関する Python 関連の問題を排除する前提条件です。
  - リモート展開では、既存の MDM セットアップを Microsoft Defender for Endpoint for Mac バージョン 101.59.50 (以降) に更新する必要があります。 MDM 経由で古い Microsoft Defender for Endpoint for Mac バージョンを macOS Monterey 12.3 (または新しいバージョン) にプッシュすると、インストールエラーが発生します。

## <a name="1015910-20122012159100"></a>101.59.10 (20.122012.15910.0)

- コマンド ライン ツールでは、検疫済みファイルを、ファイルが最初に検出された場所以外の場所に復元できます。 これは、 を使用して実行できます `mdatp threat quarantine restore --id [threat-id] --path [destination-folder]`。
- Thunderbolt 3 で接続されたデバイスを処理する拡張デバイス制御
- 無効なベンダーの ID と製品の ID を含むデバイス制御ポリシーの処理が改善されました。 このバージョンより前のバージョンでは、ポリシーに 1 つ以上の無効な ID が含まれている場合、ポリシー全体が無視されていました。 このバージョンから開始すると、ポリシーの無効な部分だけが無視されます。 ポリシーに関する問題は、 を通じて表面化されます `mdatp device-control removable-media policy list`。
- バグ修正

## <a name="1015662-20121122156620"></a>101.56.62 (20.121122.15662.0)

- バグ修正

## <a name="1015635-20121121156350"></a>101.56.35 (20.121121.15635.0)

- アプリケーションの名前が "Microsoft Defender ATP" から "Microsoft Defender" に変更されました。 エンド ユーザーは、次の変更を確認します。
  - アプリケーションのインストール パスがからに変更 `/Application/Microsoft Defender ATP.app` されました `/Applications/Microsoft Defender.app`。
  - ユーザー エクスペリエンス内で、"Microsoft Defender ATP" の発生が "Microsoft Defender" に置き換えられた
- Microsoft Defender for Endpoint for Mac で配布されているネットワーク コンテンツ フィルターが原因で、一部の VPN アプリケーションが接続できない問題を解決しました
- macOS 12.2 beta 2 で検出された問題に対処し、オペレーティング システム (OS) が変更され、特定の特性を持つパッケージのインストールを妨げるインストール パッケージを開くことができません。 この OS の変更は、macOS 12.2 の最終リリースには含まれていないと思えますが、将来の macOS バージョンで再導入される可能性があります。 そのため、すべてのエンタープライズ管理者は、管理コンソールの Microsoft Defender for Endpoint パッケージをこの製品バージョン (または新しいバージョン) に更新するようにお勧めしています。
- 一部の M1 デバイスで、製品が無効なマルウェア対策定義でスタックし、正常に一連の定義に更新できない問題に対処しました。
- `mdatp health` 出力は、 `full_disk_access_enabled` Microsoft Defender for Endpoint for Mac のすべてのコンポーネントにフル ディスク アクセスが許可されているかどうかを判断するために使用できる追加の属性を使用して拡張されました。
- バグ修正&パフォーマンスの向上

## <a name="1015416-20121111154160"></a>101.54.16 (20.121111.15416.0)

- macOS 10.14 (Mojave) はサポートされなくなりました
- 製品設定が MDM を介して管理者によって管理を停止すると、管理前の値 (エンド ユーザーがローカルに構成した値、またはそのようなローカル値が明示的に指定されていない場合は、製品で使用される既定値) に戻ります。 この変更の前に、設定の管理が停止した後、その管理値は保持され、製品で引き続き使用されました。
- バグ修正&パフォーマンスの向上

## <a name="1014925-20121092149250"></a>101.49.25 (20.121092.14925.0)

- コマンド ライン ツールに新しいスイッチを追加し、オンデマンド スキャン中にアーカイブをスキャンするかどうかを制御しました。 これは、 を使用して構成できます `mdatp config scan-archives --value [enabled/disabled]`。 既定では、 に設定されています `enabled`。
- バグ修正

## <a name="1014727-20121082147270"></a>101.47.27 (20.121082.14727.0)

- macOS Mojave および macOS Catalina のシャットダウン時に発生するシステムのフリーズを修正する

## <a name="1014384-20121082143840"></a>101.43.84 (20.121082.14384.0)

- macOS 12 の候補ビルド (モントレー)
- バグ修正

## <a name="1014110-20121072141100"></a>101.41.10 (20.121072.14110.0)

- コマンド ライン ツールに新しいスイッチを追加しました。
  - オンデマンド スキャンの並列処理の程度を制御します。 これは、 を使用して構成できます `mdatp config maximum-on-demand-scan-threads --value [number-between-1-and-64]`。 既定では、並列処理の程度が `2` 使用されます。
  - セキュリティ インテリジェンス更新プログラムが有効または無効にされた後のスキャンを制御します。 これは、 を使用して構成できます `mdatp config scan-after-definition-update --value [enabled/disabled]`。 既定では、 に設定されています `enabled`。
- 製品ログ レベルを変更するには、昇格が必要になります。
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

- [macOS のデバイスコントロール](mac-device-control-overview.md) が一般提供中
- macOS 11 の状態メニューからクイック スキャンを開始できない問題に対処しました (Big Sur)
- その他のバグ修正

## <a name="1013269-20121042132690"></a>101.32.69 (20.121042.13269.0)

- Microsoft Defender for Endpoint および他のアプリケーションからキーチェーンに同時にアクセスすると、キーチェーンが破損する可能性がある問題に対処しました。

## <a name="1012964-20121042129640"></a>101.29.64 (20.121042.12964.0)

- このバージョンから、コマンド ライン クライアントを介してトリガーされるオンデマンド ウイルス対策スキャン中に検出された脅威は自動的に修復されます。 ユーザー インターフェイスを介してトリガーされるスキャン中に検出された脅威には、手動操作が必要です。
- `mdatp diagnostic real-time-protection-statistics` 2 つの追加スイッチがサポートされます。
  - `--sort`: スキャンされたファイルの総数で降順に出力を並べ替える
  - `--top N`: 上位 N の結果を表示します (指定されている場合 `--sort` にのみ機能します)
- パフォーマンスの向上 (特に YARN を使用する場合) &修正

## <a name="1012750-20121022127500"></a>101.27.50 (20.121022.12750.0)

- macOS Catalina 以前の Apple 証明書の有効期限に対応するように修正しました。 この修正プログラムは、脅威&管理 (TVM) 機能を復元します。

## <a name="1012569-20121022125690"></a>101.25.69 (20.121022.12569.0)

- Microsoft Defender for Endpoint on macOS は、米国政府機関のお客様向けプレビューで利用できます。 詳細については、「 [Microsoft Defender for Endpoint for US Government customers」を参照してください](gov.md)。
- パフォーマンスの向上 (特に、XCode Simulator アプリを使用する場合の状況) は、&修正します。

## <a name="1012364-20121021123640"></a>101.23.64 (20.121021.12364.0)

- コマンド ライン ツールに、前回のオンデマンド スキャンに関する情報を表示する新しいオプションが追加されました。 最後のオンデマンド スキャンに関する情報を表示するには、次のコマンドを実行します。 `mdatp health --details antivirus`
- バグ修正&パフォーマンスの向上

## <a name="1012279-20121012122790"></a>101.22.79 (20.121012.12279.0)

- バグ修正&パフォーマンスの向上

## <a name="1011988-20121011119880"></a>101.19.88 (20.121011.11988.0)

- バグ修正&パフォーマンスの向上

## <a name="1011948-20120121119480"></a>101.19.48 (20.120121.11948.0)

> [!NOTE]
> このリリースでは、古いコマンド ライン ツールの構文は廃止されました。 新しい構文の詳細については、「Resources」を [参照してください](mac-resources.md#configuring-from-the-command-line)。

- ネットワーク拡張機能を無効にする新しいコマンド ライン スイッチを追加しました。 `mdatp system-extension network-filter disable` このコマンドは、Microsoft Defender for Endpoint on Mac に関連する可能性があるネットワークの問題のトラブルシューティングに役立ちます。
- バグ修正&パフォーマンスの向上

## <a name="1011921-20120101119210"></a>101.19.21 (20.120101.11921.0)

- バグ修正

## <a name="1011526-20120102115260"></a>101.15.26 (20.120102.11526.0)

- macOS 11 Big Sur で実行する場合のエージェントの信頼性が向上しました
- カスタム スキャン中に AV の除外を無視する新しいコマンド ライン スイッチ (`--ignore-exclusions`) を追加しました (`mdatp scan custom`)
- バグ修正&パフォーマンスの向上

## <a name="1011375-20120101113750"></a>101.13.75 (20.120101.11375.0)

- Microsoft Defender for Endpoint がカーネル パニックに陥る macOS 11 (Big Sur) バグをトリガーした場合の条件を削除しました
- Mac 11 で実行されているエンドポイント セキュリティ システム拡張機能のメモリ リークを修正しました (Big Sur)
- バグ修正

## <a name="1011072"></a>101.10.72

- バグ修正

## <a name="1010961"></a>101.09.61

- フィードバックを送信するオプションを無効にする [新しい管理基本設定を追加しました](mac-preferences.md#show--hide-option-to-send-feedback)
- [状態] メニュー アイコンに、製品設定が管理されているときに正常な状態が表示されます。 以前は、製品設定が管理者によって管理されているにもかかわらず、ステータス メニュー アイコンに警告またはエラー状態が表示される場合があります。
- バグ修正&パフォーマンスの向上

## <a name="1010950"></a>101.09.50

- この製品のバージョンは、macOS Big Sur 11 ベータ 9 で検証されています

- コマンド ライン ツールの新 `mdatp` しい構文が既定の構文になります。 新しい構文の詳細については、「 [Resources for Microsoft Defender for Endpoint on macOS」を参照してください。](mac-resources.md#configuring-from-the-command-line)

  > [!NOTE]
  > 古いコマンド ライン ツールの構文は、 **2021 年 1 月 1** 日に製品から削除されます。

- 診断ログ `mdatp diagnostic create` を別のディレクトリに保存できる新しいパラメーター (`--path [directory]`) を使用して拡張
- バグ修正&パフォーマンスの向上

## <a name="1010949"></a>101.09.49

- IT 管理者が管理する除外とローカル ユーザーが定義した除外を区別するためのユーザー インターフェイスの改善
- オンデマンド スキャン時の CPU 使用率の向上
- バグ修正&パフォーマンスの向上

## <a name="1010723"></a>101.07.23

- パッシブ モードとグループ ID の`mdatp --health`状態を確認するために、新しいフィールドEDR追加しました

  > [!NOTE]
  > `mdatp --health` は、将来の製品更新 `mdatp health` プログラムに置き換えられる予定です。

- 自動サンプル送信がユーザー インターフェイスで管理済みとしてマークされていないバグを修正しました
- ウイルス対策スキャン履歴内のアイテムの保持を制御するための新しい設定が追加されました。 これで、 [スキャン履歴内の](mac-preferences.md#antivirus-scan-history-retention-in-days) アイテムを保持する日数を指定し、スキャン履歴内のアイテムの最大数 [を指定できます。](mac-preferences.md#maximum-number-of-items-in-the-antivirus-scan-history)
- バグ修正

## <a name="1010663"></a>101.06.63

- バージョンで導入されたパフォーマンス回帰に対処しました `101.05.17`。 この回帰は、SMB 共有にアクセスするときに一部のお客様が見たカーネル パニックを解消するための修正プログラムで導入されました。 このコード変更を元に戻し、カーネル パニックを排除する別の方法を検討しています。

## <a name="1010517"></a>101.05.17

> [!IMPORTANT]
> コマンド ライン ツールの新しい拡張 `mdatp` 構文に取り組む必要があります。 現在、新しい構文は Insider Fast および Insider Slow 更新チャネルの既定の構文です。 この新しい構文を使用して自分自身をfamliliarizeしてください。
>
> 新しい構文と並行して古い構文をサポートし続け、今後数か月で古い構文の廃止計画に関するより多くのコミュニケーションを提供します。

- SMB ファイル共有にアクセスするときに発生するカーネル パニックに対処しました
- バグ修正&パフォーマンスの向上

## <a name="1010516"></a>101.05.16

- スキャンされたファイルの数を大幅に削減するクイック スキャン ロジックの改善
- コマンド ライン [ツールのオート](mac-resources.md#how-to-enable-autocompletion) コンプリート サポートを追加しました
- バグ修正

## <a name="1010312"></a>101.03.12

- バグ修正&パフォーマンスの向上

## <a name="1010154"></a>101.01.54

- タイム マシンとの互換性に関する改善点
- アクセシビリティの改善点
- バグ修正&パフォーマンスの向上

## <a name="1010031"></a>101.00.31

- Intune ユーザー [の製品オンボーディング エクスペリエンスの向上](/mem/intune/apps/apps-advanced-threat-protection-macos)
- ウイルス [対策の除外でワイルドカードがサポートされる](mac-exclusions.md#supported-exclusion-types)
- macOS のコンテキスト メニューからウイルス対策スキャンをトリガーする機能が追加されました。 Finder でファイルまたはフォルダーを右クリックし、[ **Microsoft Defender for Endpoint でスキャン] を選択できます。**
- インプレイス製品のダウングレードは、インストーラーによって明示的に許可されません。 ダウングレードする必要がある場合は、まず既存のバージョンをアンインストールし、デバイスを再構成します。
- バグ修正に関するその他&改善点

## <a name="1009027"></a>100.90.27

- システム全体 [の更新チャネル](mac-updates.md#set-the-channel-name) とは異なる macOS 上の Microsoft Defender for Endpoint の更新チャネルを設定できます。
- 新しい製品アイコン
- その他のユーザー エクスペリエンスの向上
- バグ修正

## <a name="1008692"></a>100.86.92

- タイム マシンとの互換性に関する改善点
- アンインストール中に製品がすべてのファイルをクリーニングしていない問題 `/Library/Application Support/Microsoft/Defender` に対処しました
- Microsoft AutoUpdate を使用して Microsoft 製品が更新された場合の製品の CPU 使用率の低下
- バグ修正に関するその他&改善点

## <a name="1008691"></a>100.86.91

> [!CAUTION]
> macOS デバイスに対して最も完全な保護を確保し、Apple が [current - 2] より古い OS バージョンへの macOS ネイティブ セキュリティ更新プログラムの配信を停止するに合わせ、MDATP for Mac の展開と更新プログラムは macOS Sierra [10.12] でサポートされなくなりました。 MDATP for Mac の更新プログラムと拡張機能は、バージョン Catalina [10.15]、Mojave [10.14]、High Sierra [10.13] を実行しているデバイスに配信されます。
>
> MDATP for Mac がシエラ [10.12] デバイスに既に展開されている場合は、保護を失うリスクを排除するために最新の macOS バージョンにアップグレードしてください。

- バグ修正&パフォーマンスの向上

## <a name="1008373"></a>100.83.73

- 除外の管理、脅威の種類の設定[](mac-preferences.md#exclusion-merge-policy)の管理、および禁止[](mac-preferences.md#threat-type-settings-merge-policy)された脅威アクションに関する IT 管理者向けコントロール[の追加](mac-preferences.md#disallowed-threat-actions)
- デバイスでフル ディスク アクセスが有効になっていない場合は、状態メニューに警告が表示されます。
- バグ修正&パフォーマンスの向上

## <a name="1008260"></a>100.82.60

- 製品が定義の更新後に開始できない問題に対処しました。

## <a name="1008042"></a>100.80.42

- バグ修正

## <a name="1007942"></a>100.79.42

- Mac 上の Microsoft Defender for Endpoint がタイム マシンに干渉する場合がある問題を修正しました
- バックエンド サービスとの接続をテストするためにコマンド ライン ユーティリティに新しいスイッチを追加しました

  ```bash
  mdatp connectivity test
  ```

- ユーザー インターフェイスで完全な脅威履歴を表示する機能が追加されました (保護履歴 **ビューからアクセス** できます)
- バグ修正&パフォーマンスの向上

## <a name="1007215"></a>100.72.15

- バグ修正

## <a name="1007099"></a>100.70.99

- 一部のユーザーがリアルタイム保護が有効になっているときに macOS Catalina にアップグレードする機能に影響を与える問題に対処しました。 この散発的な問題は、Catalina アップグレード パッケージ内の Microsoft Defender for Endpoint locking ファイルが脅威のスキャン中に発生し、アップグレード シーケンスでエラーが発生しました。

## <a name="1006899"></a>100.68.99

- パッシブ モードで実行するウイルス対策機能を構成する機能 [が追加されました](mac-preferences.md#enforcement-level-for-antivirus-engine)
- バグ修正&パフォーマンスの向上

## <a name="1006528"></a>100.65.28

- macOS Catalina のサポートが追加されました

  > [!CAUTION]
  > macOS 10.15 (Catalina) には、新しいセキュリティとプライバシーの強化が含まれている。 このバージョンでは、既定では、アプリケーションは明示的な同意なしにディスク上の特定の場所 (ドキュメント、ダウンロード、デスクトップなど) にアクセスできません。 この同意がない場合、Microsoft Defender for Endpoint はデバイスを完全に保護できません。
  >
  > この同意を付与するメカニズムは、Microsoft Defender for Endpoint の展開方法によって異なります。
  >
  > - 手動展開については、「手動展開」の「更新された手順」 [を参照](mac-install-manually.md#how-to-allow-full-disk-access) してください。
  > - 管理展開については、「[JAMF](mac-install-with-jamf.md) ベースの展開」および「Microsoft Intune展開」[の更新された手順を参照](mac-install-with-intune.md#create-system-configuration-profiles)してください。

- バグ修正&パフォーマンスの向上
