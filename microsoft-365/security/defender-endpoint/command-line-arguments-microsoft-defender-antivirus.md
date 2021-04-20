---
title: コマンド ラインを使用して Microsoft Defender ウイルス対策を管理する
description: 専用のコマンド ライン ユーティリティを使用して、Microsoft Defender ウイルス対策スキャンを実行し、次世代の保護を構成します。
keywords: Windows Defender スキャンの実行、コマンド ラインからのウイルス対策スキャンの実行、コマンド ラインからの Windows Defender スキャンの実行、mpcmdrun、Defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ksarens
manager: dansimp
ms.date: 03/19/2021
ms.technology: mde
ms.openlocfilehash: 1b357f7c1e02211f3949383a380666cb7444f814
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2021
ms.locfileid: "51764629"
---
# <a name="configure-and-manage-microsoft-defender-antivirus-with-the-mpcmdrunexe-command-line-tool"></a>Microsoft Defender Antivirus を構成および管理するには、mpcmdrun.exe コマンド ライン ツールを使用します。

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**

- [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)

専用のコマンド ライン ツールを使用して、さまざまな Microsoft Defender ウイルス対策機能 **を実行** mpcmdrun.exe。 このユーティリティは、Microsoft Defender ウイルス対策の使用を自動化する場合に便利です。 ユーティリティは で確認できます `%ProgramFiles%\Windows Defender\MpCmdRun.exe` 。 コマンド プロンプトから実行する必要があります。

> [!NOTE]
> 管理者レベルのバージョンのコマンド プロンプトを開く必要がある場合があります。 [スタート] メニューの **[コマンド プロンプト]** を検索する場合は、[管理者として **実行] を選択します**。
> 更新された Microsoft Defender プラットフォーム バージョンを実行している場合は、次 `**MpCmdRun**` の場所から実行します `C:\ProgramData\Microsoft\Windows Defender\Platform\<version>` 。

ユーティリティには、次のコマンドがあります。

```console
MpCmdRun.exe [command] [-options]
```
次に例を示します:

```console
MpCmdRun.exe -Scan -ScanType 2
``` 

| コマンド  | 説明   |
|:----|:----|
| `-?` **または** `-h`   | このツールで使用可能なすべてのオプションを表示する |
| `-Scan [-ScanType [0\|1\|2\|3]] [-File <path> [-DisableRemediation] [-BootSectorScan] [-CpuThrottling]] [-Timeout <days>] [-Cancel]` | 悪意のあるソフトウェアをスキャンします。 **ScanType の値** は **、構成** に応じて 0 **Default、-1** クイック スキャン **、-2** フル スキャン **、-3** ファイルおよびディレクトリ のカスタム スキャンです。  CpuThrottling は、ポリシーから構成された CPU 調整を受け入れ |
| `-Trace [-Grouping #] [-Level #]` | 診断トレースを開始する |
| `-GetFiles [-SupportLogLocation <path>]` | サポート情報を収集します。 「診断[データの収集」を参照](collect-diagnostic-data.md)してください。  |
| `-GetFilesDiagTrack`  | と同 `-GetFiles` じですが、一時的な DiagTrack フォルダーへの出力 |
| `-RemoveDefinitions [-All]` | インストールされているセキュリティ インテリジェンスを以前のバックアップ コピーまたは元の既定のセットに復元します。 |
| `-RemoveDefinitions [-DynamicSignatures]` | 動的にダウンロードされたセキュリティ インテリジェンスのみを削除します。 |
| `-RemoveDefinitions [-Engine]` | 以前にインストールされたエンジンを復元する |
| `-SignatureUpdate [-UNC \| -MMPC]` | 新しいセキュリティ インテリジェンス更新プログラムのチェック |
| `-Restore  [-ListAll \| [[-Name <name>] [-All] \| [-FilePath <filePath>]] [-Path <path>]]` | 検疫済みアイテムを復元または一覧表示する |
| `-AddDynamicSignature [-Path]` | 動的セキュリティ インテリジェンスを読み込む |
| `-ListAllDynamicSignatures` | 読み込まれた動的セキュリティ インテリジェンスの一覧 |
| `-RemoveDynamicSignature [-SignatureSetID]` | 動的セキュリティ インテリジェンスを削除します |
| `-CheckExclusion -path <path>` | パスが除外されているかどうかを確認する |
| `-ValidateMapsConnection` | ネットワークが Microsoft Defender ウイルス対策クラウド サービスと通信できると確認します。 このコマンドは、Windows 10 バージョン 1703 以上でのみ動作します。|


## <a name="common-errors-in-running-commands-via-mpcmdrunexe"></a>コマンドを実行する場合の一般的なエラーは、mpcmdrun.exe 

|エラー メッセージ | 考えられる理由
|:----|:----|
| `ValidateMapsConnection failed (800106BA) or 0x800106BA` | Microsoft Defender ウイルス対策サービスが無効になっています。 サービスを有効にし、もう一度やり直してください。 <br>   **注:**  Windows 10 1909 以前および Windows Server 2019 以前の場合、このサービスは以前は "Windows Defender ウイルス対策" サービスと呼ばばがありました。|
| `0x80070667` | このコマンドは `-ValidateMapsConnection` 、Windows 10 バージョン 1607 以前のコンピューター、または Windows Server 2016 以前のコンピューターから実行しています。 Windows 10 バージョン 1703 以降、または Windows Server 2019 以降のコンピューターからコマンドを実行します。|
| `'MpCmdRun' is not recognized as an internal or external command, operable program or batch file.` | ツールは、次のいずれかから実行する必要があります (プラットフォームの更新プログラムは 3 月を除いて毎月行うので、異なる `%ProgramFiles%\Windows Defender` `C:\ProgramData\Microsoft\Windows Defender\Platform\4.18.2012.4-0` `2012.4-0` 場合があります)|
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=80070005 httpcode=450)` | 十分な特権ではありません。 管理者としてコマンド プロンプト (cmd.exe) を使用します。|
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=80070006 httpcode=451)` | ファイアウォールが接続をブロックしている、または SSL インスペクションを実行しています。 |
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=80004005 httpcode=450)` | 名前解決の問題など、ネットワーク関連の問題が考えられる|
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=0x80508015` | ファイアウォールが接続をブロックしている、または SSL インスペクションを実行しています。 |
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=800722F0D` | ファイアウォールが接続をブロックしている、または SSL インスペクションを実行しています。 |
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=80072EE7 httpcode=451)` | ファイアウォールが接続をブロックしている、または SSL インスペクションを実行しています。 |

## <a name="see-also"></a>関連項目

- [Microsoft Defender ウイルス対策機能の構成](configure-microsoft-defender-antivirus-features.md)
- [ビジネスで Microsoft Defender ウイルス対策を管理する](configuration-management-reference-microsoft-defender-antivirus.md)
- [管理および構成ツールのリファレンス トピック](configuration-management-reference-microsoft-defender-antivirus.md)
- [Windows 10 の Microsoft Defender ウイルス対策](microsoft-defender-antivirus-in-windows-10.md)