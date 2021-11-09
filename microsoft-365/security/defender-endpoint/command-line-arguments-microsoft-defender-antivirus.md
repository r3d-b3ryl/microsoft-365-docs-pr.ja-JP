---
title: コマンド ラインを使用して、コマンド ラインをMicrosoft Defender ウイルス対策
description: 専用Microsoft Defender ウイルス対策を使用して、スキャンを実行し、次世代の保護を構成します。
keywords: Windows Defender スキャンの実行、コマンド ラインからのウイルス対策スキャンの実行、コマンド ラインからの Windows Defender スキャンの実行、mpcmdrun、Defender
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ksarens
manager: dansimp
ms.date: 05/24/2021
ms.technology: mde
ms.topic: how-to
ms.collection: M365-security-compliance
ms.openlocfilehash: 00420a0f6bb809d50f77013dc953386c0e426967
ms.sourcegitcommit: e09ced3e3628bf2ccb84d205d9699483cbb4b3b0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/09/2021
ms.locfileid: "60881927"
---
# <a name="configure-and-manage-microsoft-defender-antivirus-with-the-mpcmdrunexe-command-line-tool"></a>コマンド ライン Microsoft Defender ウイルス対策を使用してmpcmdrun.exeを構成および管理する

**適用対象:**

- [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)

専用のコマンド ライン ツール を使用して、Microsoft Defender ウイルス対策でさまざまな **機能を実行** mpcmdrun.exe。 このユーティリティは、タスクを自動化する場合Microsoft Defender ウイルス対策です。 ユーティリティは で確認できます `%ProgramFiles%\Windows Defender\MpCmdRun.exe` 。 コマンド プロンプトから実行します。

> [!TIP]
> 管理者レベルのバージョンのコマンド プロンプトを開く必要がある場合があります。 コマンド プロンプトを **検索するときに**、[管理者として実行スタート メニューを **選択します**。 更新された Microsoft Defender マルウェア対策プラットフォームのバージョンを実行している場合は、次 `MpCmdRun` の場所から実行します `C:\ProgramData\Microsoft\Windows Defender\Platform\<antimalware platform version>` 。 マルウェア対策プラットフォームの詳細については、「更新プログラムとベースラインMicrosoft Defender ウイルス対策[を参照してください](manage-updates-baselines-microsoft-defender-antivirus.md)。

MpCmdRun ユーティリティは、次の構文を使用します。

```console
MpCmdRun.exe [command] [-options]
```

次に例を示します:

```console
MpCmdRun.exe -Scan -ScanType 2
```

この例では、MpCmdRun ユーティリティはデバイスで完全なウイルス対策スキャンを開始します。

## <a name="commands"></a>コマンド

|コマンド|説明|
|---|---|
|`-?`**または** `-h`|MpCmdRun ツールで使用可能なすべてのオプションを表示する|
|`-Scan [-ScanType [<value>]] [-File <path> [-DisableRemediation] [-BootSectorScan] [-CpuThrottling]] [-Timeout <days>] [-Cancel]`|悪意のあるソフトウェアをスキャンします。 **ScanType の値は次** のとおりです。<p>**0** 構成に応じて既定<p>**1** クイック スキャン<p>**2** フル スキャン<p>**3** ファイルとディレクトリのカスタム スキャン。<p>CpuThrottling はポリシー構成に従って実行されます|
|`-Trace [-Grouping #] [-Level #]`|診断トレースを開始する|
|`-GetFiles [-SupportLogLocation <path>]`|サポート情報を収集します。 「診断[データの収集」を参照](collect-diagnostic-data.md)してください。|
|`-GetFilesDiagTrack`|と同 `-GetFiles` じですが、一時的な DiagTrack フォルダーへの出力|
|`-RemoveDefinitions [-All]`|インストールされているセキュリティ インテリジェンスを以前のバックアップ コピーまたは元の既定のセットに復元します。|
|`-RemoveDefinitions [-DynamicSignatures]`|動的にダウンロードされたセキュリティ インテリジェンスのみを削除します。|
|`-RemoveDefinitions [-Engine]`|以前にインストールされたエンジンを復元する|
|`-SignatureUpdate [-UNC \|-MMPC]`|新しいセキュリティ インテリジェンス更新プログラムのチェック|
|`-Restore  [-ListAll \|[[-Name <name>] [-All] \|[-FilePath <filePath>]] [-Path <path>]]`|検疫済みアイテムを復元または一覧表示する|
|`-AddDynamicSignature [-Path]`|動的セキュリティ インテリジェンスを読み込む|
|`-ListAllDynamicSignatures`|読み込まれた動的セキュリティ インテリジェンスの一覧|
|`-RemoveDynamicSignature [-SignatureSetID]`|動的セキュリティ インテリジェンスを削除します|
|`-CheckExclusion -path <path>`|パスが除外されているかどうかを確認する|
|`-ValidateMapsConnection`|ネットワークがクラウド サービスと通信Microsoft Defender ウイルス対策します。 このコマンドは、バージョン 1703 Windows 10上でのみ機能します。|

## <a name="common-errors-in-running-commands-via-mpcmdrunexe"></a>コマンドを実行する場合の一般的なエラーは、mpcmdrun.exe

次の表に、MpCmdRun ツールの使用中に発生する可能性がある一般的なエラーの一覧を示します。

|エラー メッセージ|考えられる理由|
|---|---|
|**ValidateMapsConnection が失敗しました (800106BA)** **または** 0x800106BA|サービスMicrosoft Defender ウイルス対策無効になっています。 サービスを有効にし、もう一度やり直してください。 アプリケーションの再有効化に関するヘルプがMicrosoft Defender ウイルス対策、エンドポイント[の再インストール/有効化Microsoft Defender ウイルス対策を参照してください](switch-to-microsoft-defender-setup.md#reinstallenable-microsoft-defender-antivirus-on-your-endpoints)。<p> **ヒント**: 1909 Windows 10以前、および Windows Server 2019 以前の場合、このサービスは以前は Windows Defender ウイルス対策 と *呼ばWindows Defender ウイルス対策。*|
|**0x80070667**|このコマンドは、バージョン 1607 以前Windows 10または以前のコンピューター `-ValidateMapsConnection` Windows Server 2016実行しています。 バージョン 1703 以降Windows 10サーバー 2019 以降Windowsコマンドを実行します。|
|**MpCmdRun は、内部または外部のコマンド、操作可能なプログラム、またはバッチ ファイルとして認識されません。**|ツールを実行する必要があります (プラットフォームの更新プログラムは 3 月を除いて毎月行うので、異なる `%ProgramFiles%\Windows Defender` `C:\ProgramData\Microsoft\Windows Defender\Platform\4.18.2012.4-0` `2012.4-0` 場合があります)|
|**ValidateMapsConnection が MAPS への接続を確立できなかった (hr=80070005 httpcode=450)**|コマンドは、不十分な特権を使用して試行されました。 管理者としてコマンド プロンプト (cmd.exe) を使用します。|
|**ValidateMapsConnection が MAPS への接続を確立できなかった (hr=80070006 httpcode=451)**|ファイアウォールが接続をブロックしている、または SSL インスペクションを実行しています。|
|**ValidateMapsConnection が MAPS への接続を確立できなかった (hr=80004005 httpcode=450)**|名前解決の問題など、ネットワーク関連の問題が考えられる|
|**ValidateMapsConnection が MAPS への接続を確立できなかった (hr=0x80508015**|ファイアウォールが接続をブロックしている、または SSL インスペクションを実行しています。|
|**ValidateMapsConnection が MAPS への接続を確立できなかった (hr=800722F0D**|ファイアウォールが接続をブロックしている、または SSL インスペクションを実行しています。|
|**ValidateMapsConnection が MAPS への接続を確立できなかった (hr=80072EE7 httpcode=451)**|ファイアウォールが接続をブロックしている、または SSL インスペクションを実行しています。|

## <a name="see-also"></a>関連項目

- [Microsoft Defender ウイルス対策機能を構成する](configure-microsoft-defender-antivirus-features.md)
- [Microsoft Defender ウイルス対策 ネットワーク接続を構成および検証する](configure-network-connections-microsoft-defender-antivirus.md)
- [管理および構成ツールのリファレンス トピック](configuration-management-reference-microsoft-defender-antivirus.md)
