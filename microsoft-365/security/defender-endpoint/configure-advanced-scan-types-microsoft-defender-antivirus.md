---
title: Microsoft Defender AV のスキャン オプションを構成する
description: 電子メール ストレージ ファイル、バックアップまたは再解析ポイント、ネットワーク ファイル、アーカイブ ファイル (.zip ファイルなど) をスキャンする Microsoft Defender AV を構成できます。
keywords: 高度なスキャン、スキャン、電子メール、アーカイブ、zip、rar、アーカイブ、再解析スキャン
search.product: eADQiWindows 10XVcnh
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
ms.openlocfilehash: 625c84e79efe53cae2bc8f511726ad3f384ea505
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/13/2021
ms.locfileid: "51691071"
---
# <a name="configure-microsoft-defender-antivirus-scanning-options"></a>Microsoft Defender ウイルス対策スキャン オプションの構成

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**

- [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)

## <a name="use-microsoft-intune-to-configure-scanning-options"></a>Microsoft Intune を使用してスキャン オプションを構成する

詳細 [については、「Configure device Restriction settings in Microsoft Intune」](/intune/device-restrictions-configure) および [「Microsoft Defender Antivirus device Restriction settings for Windows 10 in Intune」](/intune/device-restrictions-windows-10#microsoft-defender-antivirus) を参照してください。

## <a name="use-microsoft-endpoint-manager-to-configure-scanning-options"></a>Microsoft Endpoint Manager を使用してスキャン オプションを構成する

Microsoft Endpoint Manager ( [現在の](/configmgr/protect/deploy-use/endpoint-antimalware-policies#scan-settings) ブランチ) の構成の詳細については、「マルウェア対策ポリシーを作成して展開する方法: スキャン設定」を参照してください。

## <a name="use-group-policy-to-configure-scanning-options"></a>グループ ポリシーを使用してスキャン オプションを構成する

次の表で説明するグループ ポリシー設定を構成するには、次の表を参照してください。

1. グループ ポリシー管理コンピューターで、グループ ポリシー [管理](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))コンソールを開き、構成するグループ ポリシー オブジェクトを右クリックし、[編集] をクリック **します**。

2. グループ ポリシー **管理エディターで、[コンピューター** の構成] に **移動し、[** 管理用 **テンプレート] をクリックします**。

3. ツリーを **Microsoft Defender** ウイルス対策> Windows コンポーネントに展開し、次の表で指定した場所を展開します。

4. 下の表で指定 **したポリシー設定** をダブルクリックし、オプションを目的の構成に設定します。 **[OK] を** クリックし、他の設定を繰り返します。

説明 | 場所と設定 | 既定の設定 (構成されていない場合) | クラスの PowerShell `Set-MpPreference` パラメーターまたは WMI `MSFT_MpPreference` プロパティ
---|---|---|---
電子メール のスキャン 電子メール [スキャンの制限を参照してください。](#ref1)| スキャン>電子メール スキャンを有効にする | 無効 | `-DisableEmailScanning`
再 [解析ポイントのスキャン](/windows/win32/fileio/reparse-points) | スキャン >再解析ポイント スキャンを有効にする | 無効 | 利用不可
マップされたネットワーク ドライブをスキャンする | スキャン > マップされたネットワーク ドライブでフル スキャンを実行する | 無効 | `-DisableScanningMappedNetworkDrivesForFullScan`
 アーカイブ ファイル (.zip ファイルや .rar ファイルなど) をスキャンします。 拡張機能 [の除外リストは、](configure-extension-file-exclusions-microsoft-defender-antivirus.md) この設定よりも優先されます。 | [スキャン> アーカイブ ファイルのスキャン] | Enabled | `-DisableArchiveScanning`
ネットワーク上のファイルをスキャンする | ネットワーク ファイル>スキャンする | 無効 | `-DisableScanningNetworkFiles`
パックされた実行可能ファイルをスキャンする | スキャン>パックされた実行可能ファイルをスキャンする | Enabled | 利用不可
フル スキャン時にのみリムーバブル ドライブをスキャンする | [スキャン>リムーバブル ドライブのスキャン] | 無効 | `-DisableRemovableDriveScanning`
スキャンするアーカイブ フォルダー内のサブフォルダーのレベルを指定する | [スキャン> アーカイブ ファイルをスキャンする最大深度を指定します。 | 0 | 利用不可
 スキャン中の CPU の最大負荷 (パーセンテージ) を指定します。 注: これはハードリミットではなく、スキャン エンジンが平均してこの最大値を超えないようにするガイダンスです。 | スキャン>スキャン中の CPU 使用率の最大割合を指定します。 | 50 |  `-ScanAvgCPULoadFactor`
 スキャンするアーカイブ ファイルの最大サイズ (キロバイト単位) を指定します。 既定値の **0** は、制限なしを適用します。 | スキャン>スキャンするアーカイブ ファイルの最大サイズを指定します。 | 制限なし | 利用不可
 スケジュールされたスキャンの CPU 優先度が低い構成 | スキャン >スケジュールされたスキャンの CPU 優先度が低いを構成する | 無効 | 利用不可
 
> [!NOTE]
> リアルタイム保護が有効になっている場合、ファイルにアクセスして実行する前にファイルがスキャンされます。 スキャンスコープには、マウントされたリムーバブル メディア上のファイル (USB ドライブなど) を含むすべてのファイルが含まれます。 スキャンを実行するデバイスでリアルタイム保護またはオンアクセス保護が有効になっている場合、スキャンにはネットワーク共有も含まれます。

## <a name="use-powershell-to-configure-scanning-options"></a>PowerShell を使用してスキャン オプションを構成する

Microsoft Defender [ウイルス対策で PowerShell](use-powershell-cmdlets-microsoft-defender-antivirus.md) を使用する方法の詳細については、「PowerShell コマンドレットと [Defender](/powershell/module/defender/) コマンドレットを使用して Microsoft Defender ウイルス対策を管理する」を参照してください。

## <a name="use-wmi-to-configure-scanning-options"></a>WMI を使用してスキャン オプションを構成する

WMI クラスを使用する場合は [、「WMIv2 API Windows Defenderを参照してください](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)。

<a id="ref1"></a>

## <a name="email-scanning-limitations"></a>電子メールのスキャンの制限

電子メール スキャンを使用すると、オンデマンドおよびスケジュールされたスキャン中に Outlook や他のメール クライアントによって使用される電子メール ファイルをスキャンできます。 電子メール ファイル内の埋め込みオブジェクト (添付ファイルやアーカイブ ファイルなど) もスキャンされます。 次のファイル形式の種類をスキャンして修復できます。

- DBX
- MBX
- MIME

Outlook 2003 以前 (アーカイブの種類が Unicode 以外に設定されている) で使用されている PST ファイルもスキャンされますが、pst ファイル内で検出された脅威を Windows Defender で修復することはできません。

Microsoft Defender Antivirus が電子メール内の脅威を検出した場合、侵害された電子メールを識別するために次の情報が表示されます。そのため、脅威を手動で修復できます。

- メールの件名
- 添付ファイル名

## <a name="related-topics"></a>関連項目

- [Microsoft Defender ウイルス対策スキャンと修復の結果をカスタマイズ、開始、および確認する](customize-run-review-remediate-scans-microsoft-defender-antivirus.md)
- [Microsoft Defender ウイルス対策スキャンの構成と実行](run-scan-microsoft-defender-antivirus.md)
- [スケジュールされた Microsoft Defender ウイルス対策スキャンを構成する](scheduled-catch-up-scans-microsoft-defender-antivirus.md)
- [Windows 10 の Microsoft Defender ウイルス対策](microsoft-defender-antivirus-in-windows-10.md)