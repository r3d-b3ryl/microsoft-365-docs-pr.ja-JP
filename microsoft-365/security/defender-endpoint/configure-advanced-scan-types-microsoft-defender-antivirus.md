---
title: Microsoft Defender ウイルス対策のスキャン オプションを構成する
description: 電子メール ストレージ ファイル、バックアップまたは再解析ポイント、ネットワーク ファイル、アーカイブされたファイル (.zip ファイルなど) をスキャンするように Microsoft Defender ウイルス対策を構成できます。
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
ms.openlocfilehash: 873ea8ee0b8f3f392a312b811b79f9a6e59f9825
ms.sourcegitcommit: d09eb780dc41a01796eb8137fbe9267231af6746
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/19/2022
ms.locfileid: "67387883"
---
# <a name="configure-microsoft-defender-antivirus-scanning-options"></a>Microsoft Defender ウイルス対策スキャン オプションを構成する

**適用対象:**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- Microsoft Defender ウイルス対策

**プラットフォーム**
- Windows 

## <a name="use-microsoft-intune-to-configure-scanning-options"></a>Microsoft Intuneを使用してスキャン オプションを構成する

詳細については、「[Microsoft Intuneでデバイスの制限設定を構成する](/intune/device-restrictions-configure)」と「Intuneの[Windows 10用の Microsoft Defender ウイルス対策デバイス制限設定」を参照](/intune/device-restrictions-windows-10#microsoft-defender-antivirus)してください。

## <a name="use-microsoft-endpoint-manager-to-configure-scanning-options"></a>Microsoft エンドポイント マネージャーを使用してスキャン オプションを構成する

Microsoft エンドポイント マネージャー (現在のブランチ) の構成の詳細については、「[マルウェア対策ポリシーを作成して展開する方法: スキャン設定](/configmgr/protect/deploy-use/endpoint-antimalware-policies#scan-settings)」を参照してください。

## <a name="use-group-policy-to-configure-scanning-options"></a>グループ ポリシーを使用してスキャン オプションを構成する

> [!TIP]
> Windows 用に提供される管理用テンプレート ファイルに含まれるコンピューターとユーザーの構成のポリシー設定を一覧表示するグループ ポリシー参照スプレッドシートをダウンロードします。 グループ ポリシー オブジェクトを編集するときにスプレッドシートを参照するように構成できます。 <br/><br/> 最新バージョンを次に示します。
> - [Windows 10 2020 年 5 月の更新プログラム (2004) のグループ ポリシー設定リファレンス スプレッドシート](https://www.microsoft.com/download/details.aspx?id=101451)
> - [グループ ポリシー 2021 年 10 月更新プログラム (21H2) Windows 11の設定参照スプレッドシート](https://www.microsoft.com/download/details.aspx?id=103506)

1. グループ ポリシー管理コンピューターで、[グループ ポリシー管理コンソール](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))を開きます。

2. 構成するグループ ポリシー オブジェクトを右クリックし、[編集] を選択 **します**。

3. **グループ ポリシー管理エディター** で **[コンピューターの構成**] に移動し、[**管理用テンプレート**] をクリックします。

4. ツリーを **Windows コンポーネント** \> **の Microsoft Defender ウイルス対策** に展開し、場所を選択します (この記事の [「設定と場所」](#settings-and-locations) を参照)。

5. ポリシー オブジェクトを編集します。

6. [ **OK] を** クリックし、その他の設定についても繰り返します。

### <a name="settings-and-locations"></a>設定と場所

|ポリシー 項目と場所|既定の設定 (構成されていない場合)|クラスの `MSFT_MpPreference` PowerShell `Set-MpPreference` パラメーターまたは WMI プロパティ|
|---|---|---|
|Emailスキャン <p> **スキャン** \>**電子メール スキャンを有効にする**<p>[Emailスキャンの制限事項を](#email-scanning-limitations)参照してください (この記事では)|無効|`-DisableEmailScanning`|
| スクリプト スキャン | Enabled  | このポリシー設定を使用すると、スクリプト スキャンを構成できます。 この設定を有効または未構成にすると、スクリプト スキャンが有効になります。 <p>[Defender/AllowScriptScanning を](/windows/client-management/mdm/policy-csp-defender)参照してください  | 
|[再解析ポイントをスキャンする](/windows/win32/fileio/reparse-points) <p> **スキャン** \>**再解析ポイントスキャンを有効にする**|無効|使用不可 <p>[Reparse ポイントを](/windows/win32/fileio/reparse-points)参照してください|
|マップされたネットワーク ドライブをスキャンする <p> **スキャン** \>**マップされたネットワーク ドライブでフル スキャンを実行する**|無効|`-DisableScanningMappedNetworkDrivesForFullScan`|
|アーカイブ ファイル (.zip ファイルや.rar ファイルなど) をスキャンします。 <p> **スキャン** \>**アーカイブ ファイルをスキャンする**|有効|`-DisableArchiveScanning` <p>[拡張機能の除外リスト](configure-extension-file-exclusions-microsoft-defender-antivirus.md)は、この設定よりも優先されます。|
|ネットワーク上のファイルをスキャンする <p> **スキャン** \>**ネットワーク ファイルをスキャンする**|無効|`-DisableScanningNetworkFiles`|
|パックされた実行可能ファイルをスキャンする <p> **スキャン** \>**パックされた実行可能ファイルをスキャンする**|有効|使用不可|
|フル スキャン時にのみリムーバブル ドライブをスキャンする <p> **スキャン** \>**リムーバブル ドライブをスキャンする**|無効|`-DisableRemovableDriveScanning`|
|スキャンするアーカイブ フォルダー内のサブフォルダーのレベルを指定する <p>**スキャン** \>**アーカイブ ファイルをスキャンする最大深度を指定する**|0|利用不可|
|スキャン中の最大 CPU 負荷 (パーセンテージ) を指定します。 <p> **スキャン** \>**スキャン中の CPU 使用率の最大割合を指定する**|50|`-ScanAvgCPULoadFactor` <p>**注**: CPU の最大負荷はハード制限ではありませんが、スキャン エンジンが平均で最大を超えないようにするためのガイダンスです。 手動でスキャンを実行すると、この設定は無視され、CPU 制限なしで実行されます。|
|スキャンするアーカイブ ファイルの最大サイズ (キロバイト単位) を指定します。 <p> **スキャン** \>**スキャンするアーカイブ ファイルの最大サイズを指定する**|制限なし|使用不可 <p>既定値の 0 は、制限なしで適用されます|
|スケジュールされたスキャンの CPU 優先度を低く構成する <p> **スキャン** \>**スケジュールされたスキャンの CPU 優先度を低く構成する**|無効|使用不可|

> [!NOTE]
> リアルタイム保護が有効になっている場合、ファイルにアクセスして実行される前にファイルがスキャンされます。 スキャン スコープには、USB ドライブなどのマウントされたリムーバブル メディア上のファイルを含むすべてのファイルが含まれます。 スキャンを実行するデバイスにリアルタイム保護またはオンアクセス保護が有効になっている場合、スキャンにはネットワーク共有も含まれます。

## <a name="use-powershell-to-configure-scanning-options"></a>PowerShell を使用してスキャン オプションを構成する

Microsoft Defender ウイルス対策で PowerShell を使用する方法の詳細については、「

- [PowerShell コマンドレットを使用して Microsoft Defender ウイルス対策を管理する](use-powershell-cmdlets-microsoft-defender-antivirus.md)
- [Microsoft Defender ウイルス対策コマンドレット](/powershell/module/defender/)

## <a name="use-wmi-to-configure-scanning-options"></a>WMI を使用してスキャン オプションを構成する

[WMIv2 API Windows Defender](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)参照してください。

## <a name="email-scanning-limitations"></a>Emailスキャンの制限事項

Emailスキャンを使用すると、オンデマンドスキャンやスケジュールスキャン中に Outlook やその他のメール クライアントによって使用される電子メール ファイルのスキャンが可能になります。 電子メール内の埋め込みオブジェクト (添付ファイルやアーカイブされたファイルなど) もスキャンされます。 次のファイル形式の種類をスキャンして修復できます。

- Dbx
- Mbx
- MIME

Outlook 2003 以前 (アーカイブの種類が非 unicode に設定されている) で使用されている PST ファイルもスキャンされますが、Microsoft Defender ウイルス対策では、PST ファイル内で検出された脅威を修復できません。

Microsoft Defender ウイルス対策によって電子メール メッセージ内の脅威が検出された場合は、侵害されたメールを識別するのに役立つ次の情報が表示されるので、脅威を手動で修復できます。

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

- [Microsoft Defender ウイルス対策のスキャンと修復の結果をカスタマイズ、開始、および確認する](customize-run-review-remediate-scans-microsoft-defender-antivirus.md)
- [オンデマンドの Microsoft Defender ウイルス対策スキャンを構成して実行する](run-scan-microsoft-defender-antivirus.md)
- [スケジュールされた Microsoft Defender ウイルス対策スキャンを構成する](scheduled-catch-up-scans-microsoft-defender-antivirus.md)
- [Microsoft Defender ウイルス対策 (Windows 10)](microsoft-defender-antivirus-in-windows-10.md)
