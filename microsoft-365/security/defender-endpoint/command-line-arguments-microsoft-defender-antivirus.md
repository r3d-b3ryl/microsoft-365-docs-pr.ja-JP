---
title: コマンドラインを使用して Microsoft Defender ウイルス対策を管理する
description: Microsoft Defender ウイルス対策スキャンを実行し、専用のコマンドライン ユーティリティを使用して次世代の保護を構成します。
keywords: windows defender scan を実行、コマンド ラインからウイルス対策スキャンを実行、コマンド ライン、mpcmdrun、defender
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
ms.openlocfilehash: d459c87f7d996d70d37e84f4e21bc261c720b443
ms.sourcegitcommit: ebbe8713297675db5dcb3e0d9c3ae5e746b99196
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2022
ms.locfileid: "65418678"
---
# <a name="configure-and-manage-microsoft-defender-antivirus-with-the-mpcmdrunexe-command-line-tool"></a>mpcmdrun.exe コマンドライン ツールを使用して Microsoft Defender Antivirus を構成および管理する

**適用対象:**

- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- Microsoft Defender ウイルス対策 

**プラットフォーム**
- Windows

専用のコマンドライン ツール **mpcmdrun.exe** を使用して、Microsoft Defender Antivirus でさまざまな機能を実行できます。 このユーティリティは、Microsoft Defender Antivirus タスクを自動化する場合に役立ちます。 ユーティリティは `%ProgramFiles%\Windows Defender\MpCmdRun.exe` で確認できます。 コマンド プロンプトから実行します。

> [!TIP]
> 管理者レベルのバージョンのコマンド プロンプトを開く必要がある場合があります。 **[スタート]** メニューで [コマンドプロンプト] を検索する場合は、**[管理者として実行]** を選択します。 更新された Microsoft Defender マルウェア対策プラットフォームのバージョンを実行している場合は、次の場所から `MpCmdRun` を実行します: `C:\ProgramData\Microsoft\Windows Defender\Platform\<antimalware platform version>`。 詳細については、「[Microsoft Defender ウイルス対策の更新プログラムとベースライン](manage-updates-baselines-microsoft-defender-antivirus.md)」を参照してください。

MpCmdRun ユーティリティは、次の構文を使用します。

```console
MpCmdRun.exe [command] [-options]
```

次に例を示します。

```console
MpCmdRun.exe -Scan -ScanType 2
```

この例では、MpCmdRun ユーティリティはデバイスで完全なウイルス対策スキャンを開始します。

## <a name="commands"></a>コマンド

|コマンド|説明|
|---|---|
|`-?` **または** `-h`|MpCmdRun ツールで使用可能なすべてのオプションを表示する|
|`-Scan [-ScanType [<value>]] [-File <path> [-DisableRemediation] [-BootSectorScan] [-CpuThrottling]] [-Timeout <days>] [-Cancel]`|悪意のあるソフトウェアをスキャンします。 **ScanType** の値は次のとおりです。<p>**0** 構成に応じて既定<p>**1** クイック スキャン<p>**2** フル スキャン<p>**3** ファイルとディレクトリのカスタム スキャン。<p>CpuThrottling はポリシー構成に従って実行されます|
|`-Trace [-Grouping #] [-Level #]`|診断トレースを開始する|
|`-GetFiles [-SupportLogLocation <path>]`|サポート情報を収集します。 「[診断データの収集](collect-diagnostic-data.md)」を参照してください。|
|`-GetFilesDiagTrack`|`-GetFiles` と同じですが、一時的な DiagTrack フォルダーに出力します|
|`-RemoveDefinitions [-All]`|インストールされているセキュリティ インテリジェンスを以前のバックアップ コピーまたは元の既定のセットに復元します。|
|`-RemoveDefinitions [-DynamicSignatures]`|動的にダウンロードされたセキュリティ インテリジェンスのみを削除します。|
|`-RemoveDefinitions [-Engine]`|以前にインストールされたエンジンを復元する|
|`-SignatureUpdate [-UNC \|-MMPC]`|新しいセキュリティ インテリジェンス更新プログラムのチェック|
|`-Restore  [-ListAll \|[[-Name <name>] [-All] \|[-FilePath <filePath>]] [-Path <path>]]`|検疫済みアイテムを復元または一覧表示する|
|`-AddDynamicSignature [-Path]`|動的セキュリティ インテリジェンスを読み込む|
|`-ListAllDynamicSignatures`|読み込まれた動的セキュリティ インテリジェンスの一覧|
|`-RemoveDynamicSignature [-SignatureSetID]`|動的セキュリティ インテリジェンスを削除します|
|`-CheckExclusion -path <path>`|パスが除外されているかどうかを確認する|
|`-ValidateMapsConnection`|ネットワークが Microsoft Defender Antivirus クラウド サービスと通信できることを確認します。 このコマンドは、Windows 10 バージョン 1703 以降でのみ機能します。|

## <a name="common-errors-in-running-commands-via-mpcmdrunexe"></a>mpcmdrun.exe 経由でコマンドを実行する際の一般的なエラー

次の表に、MpCmdRun ツールの使用中に発生する可能性がある一般的なエラーの一覧を示します。

|エラー メッセージ|考えられる理由|
|---|---|
|**ValidateMapsConnection が失敗しました (800106BA)** または **0x800106BA**|Microsoft Defender ウイルス対策 サービスが無効になっています。 サービスを有効にし、もう一度やり直してください。 Microsoft Defender ウイルス対策を再度有効にする方法についてサポートが必要な場合は、「[エンドポイントでのMicrosoft Defender ウイルス対策の再インストール/有効化](switch-to-mde-phase-2.md#reinstallenable-microsoft-defender-antivirus-on-your-endpoints)」を参照してください。<p> **ヒント**: Windows 10 1909 以前、および Windows Server 2019 以前では、このサービスは以前は *Windows Defender ウイルス対策* と呼ばれていました。|
|**0x80070667**|Windows 10 バージョン 1607 以前、または Windows Server 2016 以前のコンピューターから `-ValidateMapsConnection` コマンドを実行しています。 Windows 10 バージョン 1703 以降、または Windows Server 2019 以降のマシンからコマンドを実行します。|
|**MpCmdRun は、内部または外部のコマンド、操作可能なプログラム、またはバッチ ファイルとして認識されません。**|ツールは `%ProgramFiles%\Windows Defender` または `C:\ProgramData\Microsoft\Windows Defender\Platform\4.18.2012.4-0` のいずれかから実行する必要があります (プラットフォームの更新は 3 月を除いて毎月行われるため、`2012.4-0` は異なる場合があります)|
|**ValidateMapsConnection は MAPS への接続を確立できませんでした (hr=80070005 httpcode=450)**|コマンドは、不十分な特権を使用して試行されました。 管理者としてコマンド プロンプト (cmd.exe) を使用します。|
|**ValidateMapsConnection は MAPS への接続を確立できませんでした (hr=80070006 httpcode=451)**|ファイアウォールが接続をブロックしている、または SSL インスペクションを実行しています。|
|**ValidateMapsConnection は MAPS への接続を確立できませんでした (hr=80004005 httpcode=450)**|名前解決の問題など、ネットワーク関連の問題が考えられます|
|**ValidateMapsConnection は MAPS への接続を確立できませんでした (hr=0x80508015**|ファイアウォールが接続をブロックしている、または SSL インスペクションを実行しています。|
|**ValidateMapsConnection は MAPS への接続を確立できませんでした (hr=800722F0D**|ファイアウォールが接続をブロックしている、または SSL インスペクションを実行しています。|
|**ValidateMapsConnection は MAPS への接続を確立できませんでした (hr=80072EE7 httpcode=451)**|ファイアウォールが接続をブロックしている、または SSL インスペクションを実行しています。|

> [!TIP]
> 他のプラットフォームのウイルス対策関連情報を探している場合は、次を参照してください。
> - [macOS 上で Microsoft Defender for Endpoint 用の基本設定を設定する](mac-preferences.md)
> - [Mac 用 Microsoft Defender for Endpoint](microsoft-defender-endpoint-mac.md)
> - [Intune の Microsoft Defender ウイルス対策の macOS ウイルス対策ポリシー設定](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [Linux 上で Microsoft Defender for Endpoint 用の基本設定を設定する](linux-preferences.md)
> - [Linux 用 Microsoft Defender for Endpoint](microsoft-defender-endpoint-linux.md)
> - [Android 機能用 Defender for Endpoint を構成する](android-configure.md)
> - [iOS 機能用 Microsoft Defender for Endpoint を構成する](ios-configure-features.md)

## <a name="see-also"></a>関連項目

- [Microsoft Defender ウイルス対策機能を構成する](configure-microsoft-defender-antivirus-features.md)
- [Microsoft Defender ウイルス対策 ネットワーク接続を構成および検証する](configure-network-connections-microsoft-defender-antivirus.md)
- [管理および構成ツールのリファレンス トピック](configuration-management-reference-microsoft-defender-antivirus.md)
