---
title: Microsoft Defender ウイルス対策のスキャン オプションを構成する
description: 電子メール ストレージ ファイル、バックアップまたは再解析ポイント、ネットワーク ファイル、アーカイブされたファイル (.zip ファイルなど) をスキャンするように Microsoft Defender AV を構成できます。
keywords: 高度なスキャン, スキャン, 電子メール, アーカイブ, zip,rar, アーカイブ, 再解析スキャン
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
ms.date: 12/03/2021
ms.collection: M365-security-compliance
ms.topic: how-to
ms.openlocfilehash: 5060a05e485db18f8276ecd2ec592ea3873a83b2
ms.sourcegitcommit: ebbe8713297675db5dcb3e0d9c3ae5e746b99196
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2022
ms.locfileid: "65419926"
---
# <a name="configure-microsoft-defender-antivirus-scanning-options"></a>Microsoft Defender ウイルス対策スキャン オプションを構成する

**適用対象:**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- Microsoft Defender ウイルス対策

**プラットフォーム**
- Windows 

## <a name="use-microsoft-intune-to-configure-scanning-options"></a>Microsoft Intuneを使用してスキャン オプションを構成する

詳細については、「[Microsoft Intuneでデバイスの制限設定を構成](/intune/device-restrictions-configure)する」および[「IntuneのWindows 10のデバイス制限設定をMicrosoft Defender ウイルス対策](/intune/device-restrictions-windows-10#microsoft-defender-antivirus)する」を参照してください。

## <a name="use-microsoft-endpoint-manager-to-configure-scanning-options"></a>Microsoft エンドポイント マネージャーを使用してスキャン オプションを構成する

Microsoft エンドポイント マネージャー (現在のブランチ) の構成の詳細については、「[マルウェア対策ポリシーを作成して展開する方法: スキャン設定](/configmgr/protect/deploy-use/endpoint-antimalware-policies#scan-settings)」を参照してください。

## <a name="use-group-policy-to-configure-scanning-options"></a>グループ ポリシーを使用してスキャン オプションを構成する

> [!TIP]
> グループ ポリシー参照スプレッドシートをダウンロードします。このスプレッドシートには、Windows用に配信される管理用テンプレート ファイルに含まれるコンピューターとユーザーの構成のポリシー設定が一覧表示されます。 グループ ポリシー オブジェクトを編集するときにスプレッドシートを参照するように構成できます。 <br/><br/> 最新バージョンを次に示します。
> - [Windows 10 2020 年 5 月更新 (2004 年) のグループ ポリシー 設定参照スプレッドシート](https://www.microsoft.com/download/details.aspx?id=101451)
> - [Windows 11 2021 年 10 月更新 (21H2) のグループ ポリシー 設定参照スプレッドシート](https://www.microsoft.com/download/details.aspx?id=103506)

1. グループ ポリシー管理コンピューターで、[グループ ポリシー管理コンソール](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))を開きます。

2. 構成するグループ ポリシー オブジェクトを右クリックし、[編集] を選択 **します**。

3. **グループ ポリシー管理エディター** で **[コンピューターの構成**] に移動し、[**管理用テンプレート**] をクリックします。

4. ツリーを展開して **Microsoft Defender ウイルス対策コンポーネント** \> **をWindows** し、場所を選択します (この記事の [設定と場所](#settings-and-locations)を参照してください)。

5. ポリシー オブジェクトを編集します。

6. [ **OK] を** クリックし、その他の設定についても繰り返します。

### <a name="settings-and-locations"></a>設定と場所

|ポリシー 項目と場所|既定の設定 (構成されていない場合)|クラスの `MSFT_MpPreference` PowerShell `Set-MpPreference` パラメーターまたは WMI プロパティ|
|---|---|---|
|電子メール スキャン <p> **スキャン** \>**電子メール スキャンを有効にする**<p>[電子メール スキャンの制限事項を](#email-scanning-limitations)参照してください (この記事では)|無効|`-DisableEmailScanning`|
| スクリプト スキャン | Enabled  | このポリシー設定を使用すると、スクリプト スキャンを構成できます。 この設定を有効または未構成にすると、スクリプト スキャンが有効になります。 <p>[Defender/AllowScriptScanning を](/windows/client-management/mdm/policy-csp-defender)参照してください  | 
|[再解析ポイントをスキャンする](/windows/win32/fileio/reparse-points) <p> **スキャン** \>**再解析ポイントスキャンを有効にする**|無効|利用不可 <p>[Reparse ポイントを](/windows/win32/fileio/reparse-points)参照してください|
|マップされたネットワーク ドライブをスキャンする <p> **スキャン** \>**マップされたネットワーク ドライブでフル スキャンを実行する**|無効|`-DisableScanningMappedNetworkDrivesForFullScan`|
|アーカイブ ファイル (.zip ファイルや.rar ファイルなど) をスキャンします。 <p> **スキャン** \>**アーカイブ ファイルをスキャンする**|Enabled|`-DisableArchiveScanning` <p>[拡張機能の除外リスト](configure-extension-file-exclusions-microsoft-defender-antivirus.md)は、この設定よりも優先されます。|
|ネットワーク上のファイルをスキャンする <p> **スキャン** \>**ネットワーク ファイルをスキャンする**|無効|`-DisableScanningNetworkFiles`|
|パックされた実行可能ファイルをスキャンする <p> **スキャン** \>**パックされた実行可能ファイルをスキャンする**|Enabled|利用不可|
|フル スキャン時にのみリムーバブル ドライブをスキャンする <p> **スキャン** \>**リムーバブル ドライブをスキャンする**|無効|`-DisableRemovableDriveScanning`|
|スキャンするアーカイブ フォルダー内のサブフォルダーのレベルを指定する <p>**スキャン** \>**アーカイブ ファイルをスキャンする最大深度を指定する**|0|利用不可|
|スキャン中の最大 CPU 負荷 (パーセンテージ) を指定します。 <p> **スキャン** \>**スキャン中の CPU 使用率の最大割合を指定する**|50|`-ScanAvgCPULoadFactor` <p>**注**: CPU の最大負荷はハード制限ではありませんが、スキャン エンジンが平均で最大を超えないようにするためのガイダンスです。 手動でスキャンを実行すると、この設定は無視され、CPU 制限なしで実行されます。|
|スキャンするアーカイブ ファイルの最大サイズ (キロバイト単位) を指定します。 <p> **スキャン** \>**スキャンするアーカイブ ファイルの最大サイズを指定する**|無制限|利用不可 <p>既定値の 0 は、制限なしで適用されます|
|スケジュールされたスキャンの CPU 優先度を低く構成する <p> **スキャン** \>**スケジュールされたスキャンの CPU 優先度を低く構成する**|無効|利用不可|

> [!NOTE]
> リアルタイム保護が有効になっている場合、ファイルにアクセスして実行される前にファイルがスキャンされます。 スキャン スコープには、USB ドライブなどのマウントされたリムーバブル メディア上のファイルを含むすべてのファイルが含まれます。 スキャンを実行するデバイスにリアルタイム保護またはオンアクセス保護が有効になっている場合、スキャンにはネットワーク共有も含まれます。

## <a name="use-powershell-to-configure-scanning-options"></a>PowerShell を使用してスキャン オプションを構成する

Microsoft Defender ウイルス対策で PowerShell を使用する方法の詳細については、次を参照してください。

- [PowerShell コマンドレットを使用してMicrosoft Defender ウイルス対策を管理する](use-powershell-cmdlets-microsoft-defender-antivirus.md)
- [Microsoft Defender ウイルス対策 コマンドレット](/powershell/module/defender/)

## <a name="use-wmi-to-configure-scanning-options"></a>WMI を使用してスキャン オプションを構成する

[WMIv2 API Windows Defender](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)参照してください。

## <a name="email-scanning-limitations"></a>電子メール スキャンの制限事項

電子メール スキャンを使用すると、オンデマンドスキャンとスケジュールスキャン中にOutlookやその他のメール クライアントによって使用される電子メール ファイルのスキャンが可能になります。 電子メール内の埋め込みオブジェクト (添付ファイルやアーカイブされたファイルなど) もスキャンされます。 次のファイル形式の種類をスキャンして修復できます。

- DBX
- MBX
- MIME

Outlook 2003 以前 (アーカイブの種類が非 unicode に設定されている) で使用されている PST ファイルもスキャンされますが、PST ファイル内で検出された脅威を修復Microsoft Defender ウイルス対策できません。

Microsoft Defender ウイルス対策電子メール メッセージ内で脅威が検出された場合は、侵害されたメールを特定するのに役立つ次の情報が表示され、脅威を手動で修復できます。

- メールの件名
- 添付ファイル名

## <a name="scanning-mapped-network-drives"></a>マップされたネットワーク ドライブのスキャン

どの OS でも、システム レベルでマップされているネットワーク ドライブのみがスキャンされます。 ユーザー レベルのマップされたネットワーク ドライブはスキャンされません。 ユーザー レベルのマップされたネットワーク ドライブは、ユーザーがセッション内で手動でマップし、独自の資格情報を使用するネットワーク ドライブです。

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

- [Microsoft Defender ウイルス対策スキャンと修復の結果をカスタマイズ、開始、および確認する](customize-run-review-remediate-scans-microsoft-defender-antivirus.md)
- [オンデマンドの Microsoft Defender ウイルス対策スキャンを構成して実行する](run-scan-microsoft-defender-antivirus.md)
- [スケジュールされたMicrosoft Defender ウイルス対策 スキャンを構成する](scheduled-catch-up-scans-microsoft-defender-antivirus.md)
- [Microsoft Defender ウイルス対策 (Windows 10)](microsoft-defender-antivirus-in-windows-10.md)
