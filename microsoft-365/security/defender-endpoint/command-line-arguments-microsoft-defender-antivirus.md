---
title: コマンド ラインを使用して、コマンド ラインをMicrosoft Defender ウイルス対策
description: 専用Microsoft Defender ウイルス対策を使用して、スキャンを実行し、次世代の保護を構成します。
keywords: Windows Defender スキャンの実行、コマンド ラインからのウイルス対策スキャンの実行、コマンド ラインからの Windows Defender スキャンの実行、mpcmdrun、Defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ksarens
manager: dansimp
ms.date: 05/17/2021
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: eb7fa7fdf5b88bd9361176003817116bcbb1a087
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538905"
---
# <a name="configure-and-manage-microsoft-defender-antivirus-with-the-mpcmdrunexe-command-line-tool"></a>コマンド ライン Microsoft Defender ウイルス対策を使用してmpcmdrun.exeを構成および管理する

**適用対象:**

- [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)

専用のコマンド ライン Microsoft Defender ウイルス対策を使用して、さまざまな機能 **を実行** mpcmdrun.exe。 このユーティリティは、使用を自動化する場合にMicrosoft Defender ウイルス対策です。 ユーティリティは で確認できます `%ProgramFiles%\Windows Defender\MpCmdRun.exe` 。 コマンド プロンプトから実行する必要があります。

> [!NOTE]
> 管理者レベルのバージョンのコマンド プロンプトを開く必要がある場合があります。 [スタート] メニューの **[コマンド プロンプト]** を検索する場合は、[管理者として **実行] を選択します**。
> 更新された Microsoft Defender プラットフォーム バージョンを実行している場合は、次 `**MpCmdRun**` の場所から実行します `C:\ProgramData\Microsoft\Windows Defender\Platform\<antimalware platform version>` 。
> マルウェア対策プラットフォームの詳細については、「更新プログラムとベースラインMicrosoft Defender ウイルス対策[を参照してください](manage-updates-baselines-microsoft-defender-antivirus.md)。

MpCmdRun ユーティリティは、次の構文を使用します。

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
| `-Scan [-ScanType [0\|1\|2\|3]] [-File <path> [-DisableRemediation] [-BootSectorScan] [-CpuThrottling]] [-Timeout <days>] [-Cancel]` | 悪意のあるソフトウェアをスキャンします。 **ScanType の値は次** のとおりです。<p>**0** 構成に応じて既定<p>**-1** クイック スキャン<p>**-2** フル スキャン<p>**-3** ファイルとディレクトリのカスタム スキャン。<p>CpuThrottling は、ポリシーから構成された CPU 調整を受け入れ |
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
| `-ValidateMapsConnection` | ネットワークがクラウド サービスと通信Microsoft Defender ウイルス対策します。 このコマンドは、バージョン 1703 Windows 10上でのみ機能します。|


## <a name="common-errors-in-running-commands-via-mpcmdrunexe"></a>コマンドを実行する場合の一般的なエラーは、mpcmdrun.exe 

|エラー メッセージ | 考えられる理由
|:----|:----|
| `ValidateMapsConnection failed (800106BA) or 0x800106BA` | サービスMicrosoft Defender ウイルス対策無効になっています。 サービスを有効にし、もう一度やり直してください。 <br>   **注:** 1909 Windows 10以前で、サーバー 2019 Windows以前の場合、サービスは以前は Windows Defender ウイルス対策 サービス *と呼* ばばされています。|
| `0x80070667` | このコマンドは、バージョン 1607 以前Windows 10または以前のコンピューター `-ValidateMapsConnection` Windows Server 2016実行しています。 バージョン 1703 以降Windows 10サーバー 2019 以降Windowsコマンドを実行します。|
| `'MpCmdRun' is not recognized as an internal or external command, operable program or batch file.` | ツールは、次のいずれかから実行する必要があります (プラットフォームの更新プログラムは 3 月を除いて毎月行うので、異なる `%ProgramFiles%\Windows Defender` `C:\ProgramData\Microsoft\Windows Defender\Platform\4.18.2012.4-0` `2012.4-0` 場合があります)|
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=80070005 httpcode=450)` | 十分な特権ではありません。 管理者としてコマンド プロンプト (cmd.exe) を使用します。|
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=80070006 httpcode=451)` | ファイアウォールが接続をブロックしている、または SSL インスペクションを実行しています。 |
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=80004005 httpcode=450)` | 名前解決の問題など、ネットワーク関連の問題が考えられる|
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=0x80508015` | ファイアウォールが接続をブロックしている、または SSL インスペクションを実行しています。 |
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=800722F0D` | ファイアウォールが接続をブロックしている、または SSL インスペクションを実行しています。 |
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=80072EE7 httpcode=451)` | ファイアウォールが接続をブロックしている、または SSL インスペクションを実行しています。 |

## <a name="see-also"></a>関連項目

- [Microsoft Defender ウイルス対策機能を構成する](configure-microsoft-defender-antivirus-features.md)
- [ビジネスMicrosoft Defender ウイルス対策管理する](configuration-management-reference-microsoft-defender-antivirus.md)
- [管理および構成ツールのリファレンス トピック](configuration-management-reference-microsoft-defender-antivirus.md)
- [Microsoft Defender ウイルス対策 (Windows 10)](microsoft-defender-antivirus-in-windows-10.md)