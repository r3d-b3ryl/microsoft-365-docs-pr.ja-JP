---
title: Microsoft Defender for Endpointに切り替える際の問題のトラブルシューティング
description: Microsoft Defender for Endpointに切り替える際の問題のトラブルシューティング方法について説明します。
keywords: 移行, Windows Defender, 高度なエンドポイント保護, ウイルス対策, マルウェア対策, パッシブ モード, アクティブ モード, トラブルシューティング
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365solution-scenario
- M365-security-compliance
ms.topic: conceptual
ms.custom: migrationguides
ms.date: 04/01/2022
ms.reviewer: jesquive, chventou, jonix, chriggs, owtho
ms.technology: mde
ms.openlocfilehash: 8334ce03bac5b7d4518433f83ab34d5f86e71339
ms.sourcegitcommit: adea59259a5900cad5de29ddf46d1ca9e9e1c82f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/04/2022
ms.locfileid: "64634165"
---
# <a name="troubleshooting-issues-when-switching-to-microsoft-defender-for-endpoint"></a>Microsoft Defender for Endpointに切り替える際の問題のトラブルシューティング

**適用対象:**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

この記事では、Microsoft 以外のエンドポイント保護ソリューションから Microsoft Defender for Endpointに切り替える際に問題が発生しているセキュリティ管理者のトラブルシューティング情報を提供します。

## <a name="microsoft-defender-antivirus-is-getting-uninstalled-on-windows-server"></a>Windows Server でMicrosoft Defender ウイルス対策がアンインストールされる

Defender for Endpoint に切り替えると、Microsoft 以外のウイルス対策/マルウェア対策保護がアクティブ モードで開始されます。 セットアップ プロセスの一環として、パッシブ モードでMicrosoft Defender ウイルス対策を構成します。 場合によっては、Microsoft 以外のウイルス対策/マルウェア対策ソリューションによって、Windows Server でのMicrosoft Defender ウイルス対策の実行が妨げる場合があります。 実際、Microsoft Defender ウイルス対策が Windows Server から削除されたように見える場合があります。

この問題を解決するには、次の手順に従います。

1. [除外リストにMicrosoft Defender for Endpointを追加します](#add-microsoft-defender-for-endpoint-to-the-exclusion-list)。
2. [Microsoft Defender ウイルス対策を手動でパッシブ モードに設定します](#set-microsoft-defender-antivirus-to-passive-mode-manually)。

### <a name="add-microsoft-defender-for-endpoint-to-the-exclusion-list"></a>除外リストにMicrosoft Defender for Endpointを追加する

Defender for Endpoint の特定の除外は、既存の Microsoft 以外のエンドポイント保護ソリューションで定義する必要があります。 次の除外項目を必ず追加してください。

`C:\Program Files\Windows Defender Advanced Threat Protection\MsSense.exe`

`C:\Program Files\Windows Defender Advanced Threat Protection\SenseCncProxy.exe`

`C:\Program Files\Windows Defender Advanced Threat Protection\SenseSampleUploader.exe`

`C:\Program Files\Windows Defender Advanced Threat Protection\SenseIR.exe`

`C:\Program Files\Windows Defender Advanced Threat Protection\SenseCM.exe`

### <a name="set-microsoft-defender-antivirus-to-passive-mode-manually"></a>手動でMicrosoft Defender ウイルス対策をパッシブ モードに設定する

Windows Server 2019、Windows Server、バージョン 1803 以降、Windows Server 2016、または R2 Windows Server 2012では、Microsoft Defender ウイルス対策を手動でパッシブ モードに設定する必要があります。 この操作は、サーバーに複数のウイルス対策製品がインストールされていることによる問題を防ぐのに役立ちます。 PowerShell、グループ ポリシー、またはレジストリ キーを使用して Microsoft Defender ウイルス対策をパッシブ モードに設定することができます。

次のレジストリ キーを設定すると、Microsoft Defender ウイルス対策をパッシブ モードに設定できます。

パス: `HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`

名前: `ForceDefenderPassiveMode`

種類`REG_DWORD`

値: `1`

> [!NOTE]
> パッシブ モードを Windows Server 2016 および Windows Server 2012 R2 を実行するエンドポイントで動作するには、「[オンボード Windows サーバー](configure-server-endpoints.md#windows-server-2012-r2-and-windows-server-2016)」の手順に従ってこれらのエンドポイントをオンボードする必要があります。

詳細については、「[Windows Server のMicrosoft Defender ウイルス対策」を参照してください](microsoft-defender-antivirus-on-windows-server.md)。

## <a name="microsoft-defender-antivirus-seems-to-be-stuck-in-passive-mode"></a>パッシブ モードでMicrosoft Defender ウイルス対策がスタックしているように見える

パッシブ モードでMicrosoft Defender ウイルス対策スタックしている場合は、次の手順に従って手動でアクティブ モードに設定します。

1. Windows デバイスで、管理者としてレジストリ エディターを開きます。

2. `Computer\HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`に移動します。

3. 呼び出`ForceDefenderPassiveMode`された **REG_DWORD** エントリを設定または定義し、その値`0`を .

4. デバイスを再起動します。

> [!IMPORTANT]
> この手順に従った後もMicrosoft Defender ウイルス対策をアクティブ モードに設定できない場合は、[サポートにお問い合わせください](../../admin/get-help-support.md)。

## <a name="i-am-having-trouble-re-enabling-microsoft-defender-antivirus-on-windows-server-2016"></a>Windows Server 2016でMicrosoft Defender ウイルス対策を再度有効にできない

Windows Server 2016で Microsoft 以外のウイルス対策/マルウェア対策ソリューションを使用している場合は、既存のソリューションを無効またはアンインストールするMicrosoft Defender ウイルス対策が必要な場合があります。 [ Malware Protection Command-Line ユーティリティ](command-line-arguments-microsoft-defender-antivirus.md)を使用して、Windows Server 2016でMicrosoft Defender ウイルス対策を再度有効にすることができます。

1. サーバー上のローカル管理者として、コマンド プロンプトを開きます。

2. 次のコマンドを実行します。`MpCmdRun.exe -wdenable`

3. デバイスを再起動します。

## <a name="see-also"></a>関連項目

- [Microsoft Defender ウイルス対策の他のセキュリティ製品との互換性](microsoft-defender-antivirus-compatibility.md)

- [Defender for Endpoint でデバイスをWindowsするためのツールとメソッドのオンボード](configure-endpoints.md) 
