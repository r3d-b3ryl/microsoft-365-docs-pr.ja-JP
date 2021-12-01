---
title: Microsoft Defender for Endpoint に切り替える際の問題のトラブルシューティング
description: Microsoft Defender for Endpoint への切り替え時に問題をトラブルシューティングする方法について説明します。
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
- M365-security-compliance
- m365solution-migratetomdatp
- m365solution-overview
- m365solution-mcafeemigrate
- m365solution-symantecmigrate
ms.topic: conceptual
ms.custom: migrationguides
ms.date: 11/30/2021
ms.reviewer: jesquive, chventou, jonix, chriggs, owtho
ms.technology: mde
ms.openlocfilehash: bbde6e79f35bf69b29d589186054bc072124d1ea
ms.sourcegitcommit: aacf895ba20ecec4312a447ff4432e257e41edee
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/30/2021
ms.locfileid: "61234533"
---
# <a name="troubleshooting-issues-when-switching-to-microsoft-defender-for-endpoint"></a>Microsoft Defender for Endpoint に切り替える際の問題のトラブルシューティング

**適用対象:**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

この記事では、Microsoft 以外のエンドポイント保護ソリューションから Microsoft Defender for Endpoint に切り替える際に問題が発生しているセキュリティ管理者のトラブルシューティング情報を提供します。

## <a name="microsoft-defender-antivirus-is-getting-uninstalled-on-windows-server"></a>Microsoft Defender ウイルス対策が Windows Server でアンインストールされる

Defender for Endpoint に切り替える場合は、アクティブ モードで Microsoft 以外のウイルス対策/マルウェア対策保護から始まります。 セットアップ プロセスの一環として、パッシブ モードで Microsoft Defender ウイルス対策を構成します。 場合によっては、Microsoft 以外のウイルス対策/マルウェア対策ソリューションによって、Microsoft Defender ウイルス対策が Windows Server で実行されていないことがあります。 実際には、Microsoft Defender ウイルス対策が Windows Server から削除されたと見なされる可能性があります。

この問題を解決するには、次の手順を実行します。

1. [DisableAntiSpyware レジストリ キーを false に設定します](#set-the-disableantispyware-registry-key-to-false)。
2. [除外リストに Microsoft Defender for Endpoint を追加します](#add-microsoft-defender-for-endpoint-to-the-exclusion-list)。
3. [Microsoft Defender ウイルス対策をパッシブ モードに手動で設定します](#set-microsoft-defender-antivirus-to-passive-mode-manually)。

### <a name="set-the-disableantispyware-registry-key-to-false"></a>DisableAntiSpyware レジストリ キーを false に設定する

[DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware)レジストリ キーは、Microsoft Defender Antivirus を無効にし、McAfee、Symantec などの別のウイルス対策製品を展開するために、過去に使用されています。 **一般に、Windows デバイスと** エンドポイントにこのレジストリ キーを持つ必要があります。ただし、構成 *済みの* 場合は、その値を false `DisableAntiSpyware` に設定する方法を次に示します。

1. Windows Server デバイスで、[レジストリ エディター] を開きます。

2. `HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender` に移動します。

3. そのフォルダーで **、DisableAntiSpyware** という DWORD エントリを探します。
   - そのエントリが表示されない場合は、すべて設定されます。
   - **DisableAntiSpyware が表示された場合は、** 手順 4 に進みます。

4. DisableAntiSpyware DWORD を右クリックし、[変更] を **選択します**。

5. に値を設定します `0` 。 (このアクションは、レジストリ キーの値を false に *設定* します。)

> [!TIP]
> このレジストリ キーの詳細については [、「DisableAntiSpyware」を参照してください](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware)。

### <a name="add-microsoft-defender-for-endpoint-to-the-exclusion-list"></a>除外リストに Microsoft Defender for Endpoint を追加する

Defender for Endpoint の特定の除外は、既存の Microsoft 以外のエンドポイント保護ソリューションで定義する必要があります。 必ず次の除外を追加してください。

`C:\Program Files\Windows Defender Advanced Threat Protection\MsSense.exe`

`C:\Program Files\Windows Defender Advanced Threat Protection\SenseCncProxy.exe`

`C:\Program Files\Windows Defender Advanced Threat Protection\SenseSampleUploader.exe`

`C:\Program Files\Windows Defender Advanced Threat Protection\SenseIR.exe`

`C:\Program Files\Windows Defender Advanced Threat Protection\SenseCM.exe`

### <a name="set-microsoft-defender-antivirus-to-passive-mode-manually"></a>Microsoft Defender ウイルス対策をパッシブ モードに手動で設定する

Windows Server 2019、Windows Server バージョン 1803 以降、Windows Server 2016、または Windows Server 2012 R2 では、Microsoft Defender ウイルス対策をパッシブ モードに手動で設定する必要があります。 このアクションは、サーバーに複数のウイルス対策製品がインストールされている場合に発生する問題を防ぐのに役立ちます。 PowerShell、グループ ポリシー、またはレジストリ キーを使用して Microsoft Defender ウイルス対策をパッシブ モードに設定することができます。

Microsoft Defender ウイルス対策をパッシブ モードに設定するには、次のレジストリ キーを設定します。

パス: `HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`

名前: `ForceDefenderPassiveMode`

種類`REG_DWORD`

値: `1`

> [!NOTE]
> Windows Server 2016 および Windows Server 2012 R2 を実行しているエンドポイントでパッシブ モードが動作するには、オンボード Windows サーバーの指示に従って、これらのエンドポイントをオンボードする [必要があります](configure-server-endpoints.md#windows-server-2012-r2-and-windows-server-2016)。

詳細については [、「Microsoft Defender Antivirus on Windows Server」を参照してください](microsoft-defender-antivirus-on-windows-server.md)。

## <a name="i-am-having-trouble-reinstalling-microsoft-defender-antivirus-on-windows-server-2016"></a>Windows Server 2016 での Microsoft Defender ウイルス対策の再インストールで問題が発生しました

Windows Server 2016 で Microsoft 以外のウイルス対策/マルウェア対策ソリューションを使用している場合、既存のソリューションで Microsoft Defender Antivirus を無効またはアンインストールする必要がある可能性があります。 マルウェア保護ユーティリティを[ 使用](command-line-arguments-microsoft-defender-antivirus.md) Command-Line Windows Server 2016 で Microsoft Defender ウイルス対策を再び有効にできます。

1. サーバーのローカル管理者として、コマンド プロンプトを開きます。

2. 次のコマンドを実行します。`MpCmdRun.exe -wdenable`

3. デバイスを再起動します。

## <a name="see-also"></a>関連項目

- [Microsoft Defender ウイルス対策の他のセキュリティ製品との互換性](microsoft-defender-antivirus-compatibility.md)

- [Defender for Endpoint の Windows デバイスのオンボーディング ツールとメソッド](configure-endpoints.md) 