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
ms.date: 11/29/2021
ms.reviewer: jesquive, chventou, jonix, chriggs, owtho
ms.technology: mde
ms.openlocfilehash: fa8dab5e72f2e3833508bce92b5a9f0b9d699f6b
ms.sourcegitcommit: 4af23696ff8b44872330202fe5dbfd2a69d9ddbf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/30/2021
ms.locfileid: "61221586"
---
# <a name="troubleshooting-issues-when-switching-to-microsoft-defender-for-endpoint"></a>Microsoft Defender for Endpoint に切り替える際の問題のトラブルシューティング

**適用対象:**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

この記事では、Microsoft 以外のエンドポイント保護ソリューションから Microsoft Defender for Endpoint に切り替える際に問題が発生しているセキュリティ管理者のトラブルシューティング情報を提供します。

## <a name="microsoft-defender-antivirus-is-getting-uninstalled-on-windows-server"></a>Microsoft Defender ウイルス対策サーバーでアンインストールされるWindows

Defender for Endpoint に切り替える場合は、アクティブ モードで Microsoft 以外のウイルス対策/マルウェア対策保護から始まります。 セットアップ プロセスの一環として、パッシブ モードMicrosoft Defender ウイルス対策構成します。 Microsoft 以外のウイルス対策/マルウェア対策ソリューションによって、Microsoft Defender ウイルス対策サーバーで実行Windows場合があります。 実際には、サーバーから削除Microsoft Defender ウイルス対策されているWindowsがあります。

この問題を解決するには、次の手順を実行します。

1. [DisableAntiSpyware レジストリ キーを false に設定します](#set-the-disableantispyware-registry-key-to-false)。
2. [除外リストに Microsoft Defender for Endpoint を追加します](#add-microsoft-defender-for-endpoint-to-the-exclusion-list)。
3. [手動でMicrosoft Defender ウイルス対策パッシブ モードに設定します](#set-microsoft-defender-antivirus-to-passive-mode-manually)。

### <a name="set-the-disableantispyware-registry-key-to-false"></a>DisableAntiSpyware レジストリ キーを false に設定する

[DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware)レジストリ キーは、Microsoft Defender ウイルス対策 を無効にし、McAfee、Symantec などの別のウイルス対策製品を展開するために、過去に使用されています。 **一般に、Windows** デバイスとエンドポイントにこのレジストリ キーを持つ必要はありません。ただし、構成している場合は、その値を false に設定する方法を `DisableAntiSpyware` 次に示します。

1. サーバー デバイスWindowsレジストリ エディターを開きます。

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

### <a name="set-microsoft-defender-antivirus-to-passive-mode-manually"></a>パッシブ モードMicrosoft Defender ウイルス対策手動で設定する

Windows Server 2019、Windows Server バージョン 1803 以降、Windows Server 2016、または Windows Server 2012 R2 では、Microsoft Defender ウイルス対策 をパッシブ モードに手動で設定する必要があります。 このアクションは、サーバーに複数のウイルス対策製品がインストールされている場合に発生する問題を防ぐのに役立ちます。 PowerShell、グループ ポリシー、またはレジストリ キーを使用して Microsoft Defender ウイルス対策をパッシブ モードに設定することができます。

次のレジストリ Microsoft Defender ウイルス対策をパッシブ モードに設定できます。

パス: `HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`

名前: `ForceDefenderPassiveMode`

種類`REG_DWORD`

値: `1`

> [!NOTE]
> Windows Server 2016 および Windows Server 2012 R2 を実行しているエンドポイントでパッシブ モードが動作するには、オンボード Windows サーバーの指示に従って、これらのエンドポイント[をオンボードする必要があります](configure-server-endpoints.md#windows-server-2012-r2-and-windows-server-2016)。

詳細については、「Microsoft Defender ウイルス対策[サーバー Windows」 を参照してください](microsoft-defender-antivirus-on-windows-server.md)。

## <a name="see-also"></a>関連項目

- [Microsoft Defender ウイルス対策の他のセキュリティ製品との互換性](microsoft-defender-antivirus-compatibility.md)

- [Defender for Endpoint のデバイスWindowsオンボーディング ツールとメソッド](configure-endpoints.md) 