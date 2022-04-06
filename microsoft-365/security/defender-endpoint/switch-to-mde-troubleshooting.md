---
title: デバイスに切り替える際のMicrosoft Defender for Endpoint
description: デバイスへの切り替え時に問題のトラブルシューティングを行うMicrosoft Defender for Endpoint。
keywords: 移行、Windows Defender、高度なエンドポイント保護、ウイルス対策、マルウェア対策、パッシブ モード、アクティブ モード、トラブルシューティング
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
# <a name="troubleshooting-issues-when-switching-to-microsoft-defender-for-endpoint"></a>デバイスに切り替える際のMicrosoft Defender for Endpoint

**適用対象:**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

この記事では、Microsoft 以外のエンドポイント保護ソリューションからセキュリティ 保護ソリューションに切り替える際に問題が発生しているセキュリティ管理者向けトラブルシューティングMicrosoft Defender for Endpoint。

## <a name="microsoft-defender-antivirus-is-getting-uninstalled-on-windows-server"></a>Microsoft Defender ウイルス対策サーバーでアンインストールされるWindows

Defender for Endpoint に切り替える場合は、アクティブ モードで Microsoft 以外のウイルス対策/マルウェア対策保護から始まります。 セットアップ プロセスの一環として、パッシブ モードMicrosoft Defender ウイルス対策構成します。 Microsoft 以外のウイルス対策/マルウェア対策ソリューションによって、Microsoft Defender ウイルス対策サーバーで実行Windowsがあります。 実際には、サーバーから削除されたMicrosoft Defender ウイルス対策に見Windowsがあります。

この問題を解決するには、次の手順を実行します。

1. [除外Microsoft Defender for Endpointに追加します](#add-microsoft-defender-for-endpoint-to-the-exclusion-list)。
2. [パッシブ モードMicrosoft Defender ウイルス対策手動で設定します](#set-microsoft-defender-antivirus-to-passive-mode-manually)。

### <a name="add-microsoft-defender-for-endpoint-to-the-exclusion-list"></a>除外Microsoft Defender for Endpointに追加する

Defender for Endpoint の特定の除外は、既存の Microsoft 以外のエンドポイント保護ソリューションで定義する必要があります。 必ず次の除外を追加してください。

`C:\Program Files\Windows Defender Advanced Threat Protection\MsSense.exe`

`C:\Program Files\Windows Defender Advanced Threat Protection\SenseCncProxy.exe`

`C:\Program Files\Windows Defender Advanced Threat Protection\SenseSampleUploader.exe`

`C:\Program Files\Windows Defender Advanced Threat Protection\SenseIR.exe`

`C:\Program Files\Windows Defender Advanced Threat Protection\SenseCM.exe`

### <a name="set-microsoft-defender-antivirus-to-passive-mode-manually"></a>パッシブ モードMicrosoft Defender ウイルス対策手動で設定する

Windows Server 2019、Windows Server バージョン 1803 以降、Windows Server 2016、または Windows Server 2012 R2 では、Microsoft Defender ウイルス対策 をパッシブ モードに手動で設定する必要があります。 このアクションは、サーバーに複数のウイルス対策製品がインストールされている場合に発生する問題を防ぐのに役立ちます。 PowerShell、グループ ポリシー、またはレジストリ キーを使用して Microsoft Defender ウイルス対策をパッシブ モードに設定することができます。

次のレジストリ キーを設定すると、Microsoft Defender ウイルス対策をパッシブ モードに設定できます。

パス: `HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`

名前: `ForceDefenderPassiveMode`

種類`REG_DWORD`

値: `1`

> [!NOTE]
> Windows Server 2016 および Windows Server 2012 R2 を実行しているエンドポイントでパッシブ モードを動作するには、オンボード Windows サーバーの指示に従って、これらのエンドポイント[をオンボードする必要があります](configure-server-endpoints.md#windows-server-2012-r2-and-windows-server-2016)。

詳細については、「Microsoft Defender ウイルス対策 [サーバー Windowsしてください](microsoft-defender-antivirus-on-windows-server.md)。

## <a name="microsoft-defender-antivirus-seems-to-be-stuck-in-passive-mode"></a>Microsoft Defender ウイルス対策モードでスタックしているようです

パッシブ Microsoft Defender ウイルス対策スタックしている場合は、次の手順に従って手動でアクティブ モードに設定します。

1. デバイスでWindowsレジストリ エディターを管理者として開きます。

2. `Computer\HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`に移動します。

3. という名前の **REG_DWORDを設定** または `ForceDefenderPassiveMode`定義し、その値をに設定します `0`。

4. デバイスを再起動します。

> [!IMPORTANT]
> この手順を実行した後もアクティブ モードMicrosoft Defender ウイルス対策問題が発生する場合は、サポート[にお問い合わせください](../../admin/get-help-support.md)。

## <a name="i-am-having-trouble-re-enabling-microsoft-defender-antivirus-on-windows-server-2016"></a>問題が発生した場合は、Microsoft Defender ウイルス対策のWindows Server 2016

Windows Server 2016 で Microsoft 以外のウイルス対策/マルウェア対策ソリューションを使用している場合、既存のソリューションでは、Microsoft Defender ウイルス対策またはアンインストールする必要がある可能性があります。 Malware[ Protection Command-Line ユーティリティ](command-line-arguments-microsoft-defender-antivirus.md)を使用して、マルウェア保護Microsoft Defender ウイルス対策再Windows Server 2016。

1. サーバーのローカル管理者として、コマンド プロンプトを開きます。

2. 次のコマンドを実行します。`MpCmdRun.exe -wdenable`

3. デバイスを再起動します。

## <a name="see-also"></a>関連項目

- [Microsoft Defender ウイルス対策の他のセキュリティ製品との互換性](microsoft-defender-antivirus-compatibility.md)

- [Defender for Endpoint のデバイスWindowsオンボーディング ツールとメソッド](configure-endpoints.md) 
