---
title: ユーザーのスキャン オプションを構成Microsoft Defender ウイルス対策
description: Microsoft Defender AV を構成して、電子メール ストレージ ファイル、バックアップまたは再解析ポイント、ネットワーク ファイル、アーカイブ されたファイル (.zip ファイルなど) をスキャンできます。
keywords: 高度なスキャン、スキャン、電子メール、アーカイブ、zip、rar、アーカイブ、再解析スキャン
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.date: 10/19/2021
ms.collection: M365-security-compliance
ms.topic: how-to
ms.openlocfilehash: 59a578ab8b9ccae1949d59230d16b275997006c8
ms.sourcegitcommit: eb8c600d3298dca1940259998de61621e6505e69
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/24/2021
ms.locfileid: "61167876"
---
# <a name="configure-microsoft-defender-antivirus-scanning-options"></a>Microsoft Defender ウイルス対策スキャン オプションを構成する

**適用対象:**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

## <a name="use-microsoft-intune-to-configure-scanning-options"></a>スキャン オプションMicrosoft Intune構成するには、次のコマンドを使用します。

詳細については、「デバイス制限設定の[構成](/intune/device-restrictions-configure)」を参照Microsoft Intune Intune Microsoft Defender ウイルス対策デバイス制限設定Windows 10[参照してください](/intune/device-restrictions-windows-10#microsoft-defender-antivirus)。

## <a name="use-microsoft-endpoint-manager-to-configure-scanning-options"></a>スキャン オプションMicrosoft エンドポイント マネージャー構成するには、次のコマンドを使用します。

マルウェア対策ポリシー (現在のブランチMicrosoft エンドポイント マネージャー構成する方法の詳細については、「マルウェア対策ポリシーを作成して展開する方法: スキャン設定」[を参照してください](/configmgr/protect/deploy-use/endpoint-antimalware-policies#scan-settings)。

## <a name="use-group-policy-to-configure-scanning-options"></a>グループ ポリシーを使用してスキャン オプションを構成する

1. グループ ポリシー管理コンピューターで、[グループ ポリシー管理コンソール](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))を開きます。

2. 構成するグループ ポリシー オブジェクトを右クリックし、[編集] を **選択します**。

3. グループ ポリシー **管理エディターで、[コンピューター** の構成] に **移動し、[** 管理用 **テンプレート] をクリックします**。

4. ツリーを展開してWindows **コンポーネント** Microsoft Defender ウイルス対策し、場所を選択します (この記事の「設定 \> [場所](#settings-and-locations)」を参照してください)。

5. ポリシー オブジェクトを編集します。

6. **[OK] を** クリックし、他の設定を繰り返します。

### <a name="settings-and-locations"></a>設定場所

|ポリシー アイテムと場所|既定の設定 (構成されていない場合)|クラスの PowerShell `Set-MpPreference` パラメーターまたは WMI `MSFT_MpPreference` プロパティ|
|---|---|---|
|電子メールのスキャン <p> **スキャン** \>**電子メール スキャンを有効にする**<p>「 [電子メールのスキャンの制限」を](#email-scanning-limitations) 参照してください (この記事で)|無効|`-DisableEmailScanning`|
|再 [解析ポイントのスキャン](/windows/win32/fileio/reparse-points) <p> **スキャン** \>**再解析ポイントスキャンを有効にする**|無効|使用不可 <p>[「Reparse ポイント」を参照してください。](/windows/win32/fileio/reparse-points)|
|マップされたネットワーク ドライブをスキャンする <p> **スキャン** \>**マップされたネットワーク ドライブでフル スキャンを実行する**|無効|`-DisableScanningMappedNetworkDrivesForFullScan`|
|アーカイブ ファイルをスキャンする (.zipファイル.rarします。 <p> **スキャン** \>**アーカイブ ファイルのスキャン**|Enabled|`-DisableArchiveScanning` <p>拡張機能 [の除外リストは、](configure-extension-file-exclusions-microsoft-defender-antivirus.md) この設定よりも優先されます。|
|ネットワーク上のファイルをスキャンする <p> **スキャン** \>**ネットワーク ファイルのスキャン**|無効|`-DisableScanningNetworkFiles`|
|パックされた実行可能ファイルをスキャンする <p> **スキャン** \>**パックされた実行可能ファイルをスキャンする**|Enabled|使用不可|
|フル スキャン時にのみリムーバブル ドライブをスキャンする <p> **スキャン** \>**リムーバブル ドライブのスキャン**|無効|`-DisableRemovableDriveScanning`|
|スキャンするアーカイブ フォルダー内のサブフォルダーのレベルを指定する <p>**スキャン** \>**アーカイブ ファイルをスキャンする最大深度を指定する**|0|利用不可|
|スキャン中の CPU の最大負荷 (パーセンテージ) を指定します。 <p> **スキャン** \>**スキャン中の CPU 使用率の最大割合を指定する**|50|`-ScanAvgCPULoadFactor` <p>**注**: CPU の最大負荷はハード制限ではなく、スキャン エンジンが平均して最大値を超えないようにするガイダンスです。 手動でスキャンを実行すると、この設定は無視され、CPU 制限なしで実行されます。|
|スキャンするアーカイブ ファイルの最大サイズ (キロバイト単位) を指定します。 <p> **スキャン** \>**スキャンするアーカイブ ファイルの最大サイズを指定する**|無制限|使用不可 <p>既定値 0 は制限なしを適用します|
|スケジュールされたスキャンの CPU 優先度が低い構成 <p> **スキャン** \>**スケジュールされたスキャンの CPU 優先度が低い構成**|無効|使用不可|

> [!NOTE]
> リアルタイム保護が有効になっている場合、ファイルにアクセスして実行する前にファイルがスキャンされます。 スキャンスコープには、マウントされたリムーバブル メディア上のファイル (USB ドライブなど) を含むすべてのファイルが含まれます。 スキャンを実行するデバイスでリアルタイム保護またはオンアクセス保護が有効になっている場合、スキャンにはネットワーク共有も含まれます。

## <a name="use-powershell-to-configure-scanning-options"></a>PowerShell を使用してスキャン オプションを構成する

PowerShell を使用して PowerShell を使用する方法の詳細については、「Microsoft Defender ウイルス対策」

- [PowerShell コマンドレットMicrosoft Defender ウイルス対策の管理](use-powershell-cmdlets-microsoft-defender-antivirus.md)
- [Microsoft Defender ウイルス対策コマンドレット](/powershell/module/defender/)

## <a name="use-wmi-to-configure-scanning-options"></a>WMI を使用してスキャン オプションを構成する

[「WMIv2 API Windows Defender」を参照してください](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)。

## <a name="email-scanning-limitations"></a>電子メールのスキャンの制限

メール スキャンを使用すると、オンデマンドおよびスケジュールされたスキャン中に、Outlook他のメール クライアントで使用される電子メール ファイルをスキャンできます。 電子メール内の埋め込みオブジェクト (添付ファイルやアーカイブ ファイルなど) もスキャンされます。 次のファイル形式の種類をスキャンして修復できます。

- DBX
- MBX
- MIME

Outlook 2003 以前 (アーカイブの種類が Unicode 以外に設定されている) で使用される PST ファイルもスキャンされますが、Microsoft Defender ウイルス対策 は PST ファイル内で検出された脅威を修復できません。

電子Microsoft Defender ウイルス対策メッセージ内の脅威を検出した場合は、侵害された電子メールを識別するために次の情報が表示され、脅威を手動で修復できます。

- メールの件名
- 添付ファイル名

## <a name="scanning-mapped-network-drives"></a>マップされたネットワーク ドライブのスキャン

どの OS でも、システム レベルでマップされているネットワーク ドライブだけがスキャンされます。 ユーザー レベルのマップされたネットワーク ドライブはスキャンされません。 ユーザー レベルのマップされたネットワーク ドライブは、ユーザーがセッション内で手動でマップし、自分の資格情報を使用するドライブです。

## <a name="see-also"></a>関連項目

- [スキャンと修復の結果をカスタマイズ、開始Microsoft Defender ウイルス対策確認する](customize-run-review-remediate-scans-microsoft-defender-antivirus.md)
- [オンデマンドの Microsoft Defender ウイルス対策スキャンを構成して実行する](run-scan-microsoft-defender-antivirus.md)
- [スケジュールされたスキャンMicrosoft Defender ウイルス対策構成する](scheduled-catch-up-scans-microsoft-defender-antivirus.md)
- [Microsoft Defender ウイルス対策 (Windows 10)](microsoft-defender-antivirus-in-windows-10.md)
