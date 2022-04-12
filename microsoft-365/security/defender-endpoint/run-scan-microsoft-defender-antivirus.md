---
title: Microsoft Defender ウイルス対策でオンデマンド スキャンを実行してカスタマイズする
description: PowerShell、Windows Management Instrumentation を使用するか、Windows セキュリティ アプリを使用してエンドポイントで個別にオンデマンド スキャンを実行して構成する
keywords: スキャン, オンデマンド, dos, intune, インスタント スキャン
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 10/22/2021
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.collection: M365-security-compliance
ms.openlocfilehash: bca0e953b759f447e8274e8766cbcada273eb614
ms.sourcegitcommit: 4f56b4b034267b28c7dd165e78ecfb4b5390087d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/12/2022
ms.locfileid: "64788878"
---
# <a name="configure-and-run-on-demand-microsoft-defender-antivirus-scans"></a>オンデマンドの Microsoft Defender ウイルス対策スキャンを構成して実行する

**適用対象:**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- Microsoft Defender ウイルス対策

**プラットフォーム**
- Windows

個々のエンドポイントでオンデマンド スキャンを実行できます。 これらのスキャンはすぐに開始され、場所や種類などのスキャンのパラメーターを定義できます。 スキャンを実行する場合は、クイック スキャン、フル スキャン、カスタム スキャンの 3 種類から選択できます。 ほとんどの場合、クイック スキャンを使用します。 クイック スキャンでは、レジストリ キーや既知のWindowsスタートアップ フォルダーなど、システムで起動するためにマルウェアが登録されている可能性があるすべての場所が検索されます。

常時オンのリアルタイム保護と組み合わせることで、ファイルを開いたり閉じたりしたときにファイルを確認したり、ユーザーがフォルダーに移動するたびに、クイック スキャンを使用して、システムやカーネル レベルのマルウェアから始まるマルウェアに対する強力な保護を提供できます。 ほとんどの場合、クイック スキャンで十分であり、スケジュールされたスキャンまたはオンデマンド スキャンに推奨されるオプションです。 [スキャンの種類の詳細については、こちらを参照してください](schedule-antivirus-scans.md#quick-scan-full-scan-and-custom-scan)。

> [!IMPORTANT]
> Microsoft Defender ウイルス対策は、ローカル スキャンを実行するときに [LocalSystem](/windows/win32/services/localsystem-account) アカウントのコンテキストで実行されます。 ネットワーク スキャンでは、デバイス アカウントのコンテキストが使用されます。 ドメイン デバイス アカウントに共有にアクセスするための適切なアクセス許可がない場合、スキャンは機能しません。 デバイスにアクセス ネットワーク共有へのアクセス許可があることを確認します。

## <a name="use-microsoft-endpoint-manager-to-run-a-scan"></a>Microsoft エンドポイント マネージャーを使用してスキャンを実行する

1. Microsoft エンドポイント マネージャー管理センター ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) に移動し、ログインします。

2. **[エンドポイント セキュリティ** \> **ウイルス対策**] を選択します。

3. タブの一覧で、異常 **なエンドポイントWindows 10** 選択するか、異常な **エンドポイントをWindows 11します**。

4. 指定されたアクションの一覧から、[ **クイック スキャン** (推奨)] または [ **フル スキャン**] を選択します。

   [![Windows 10異常なエンドポイント タブのスキャン オプション。](images/mem-antivirus-scan-on-demand.png)](images/mem-antivirus-scan-on-demand.png#lightbox)

> [!TIP]
> Microsoft エンドポイント マネージャーを使用してスキャンを実行する方法の詳細については、「[マルウェア対策とファイアウォールのタスク: オンデマンド スキャンを実行する方法」を](/configmgr/protect/deploy-use/endpoint-antimalware-firewall#how-to-perform-an-on-demand-scan-of-computers)参照してください。

## <a name="use-the-mpcmdrunexe-command-line-utility-to-run-a-scan"></a>mpcmdrun.exe コマンド ライン ユーティリティを使用してスキャンを実行する

次 `-scan` のパラメーターを使用します。

```console
mpcmdrun.exe -scan -scantype 1
```

フル スキャンの開始やパスの定義など、ツールとその他のパラメーターの使用方法の詳細については、「[mpcmdrun.exe コマンド ライン ツールを使用してMicrosoft Defender ウイルス対策を構成および管理する](command-line-arguments-microsoft-defender-antivirus.md)」を参照してください。

## <a name="use-microsoft-intune-to-run-a-scan"></a>Microsoft Intuneを使用してスキャンを実行する

1. Microsoft エンドポイント マネージャー管理センター ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) に移動し、ログインします。

2. サイドバーで [**デバイスのすべてのデバイス**  \>] を選択し、スキャンするデバイスを選択します。

3. **[..] を選択します。詳細**。 オプションから、[ **クイック スキャン** (推奨)] または [ **フル スキャン**] を選択します。

## <a name="use-the-windows-security-app-to-run-a-scan"></a>Windows セキュリティ アプリを使用してスキャンを実行する

個々[のエンドポイントでスキャンを実行する](microsoft-defender-security-center-antivirus.md)手順については、「Windows セキュリティ アプリでスキャンを実行する」を参照してください。

## <a name="use-powershell-cmdlets-to-run-a-scan"></a>PowerShell コマンドレットを使用してスキャンを実行する

次のコマンドレットを使用します。

```PowerShell
Start-MpScan
```

Microsoft Defender ウイルス対策で PowerShell を使用する方法の詳細については、「[PowerShell コマンドレットを使用して、Microsoft Defender ウイルス対策コマンドレットと](use-powershell-cmdlets-microsoft-defender-antivirus.md) [Defender ウイルス対策コマンドレット](/powershell/module/defender/)を構成して実行する」を参照してください。

## <a name="use-windows-management-instruction-wmi-to-run-a-scan"></a>Windows管理命令 (WMI) を使用してスキャンを実行する

**MSFT_MpScan** クラスの [**Start** メソッド](/previous-versions/windows/desktop/defender/start-msft-mpscan)を使用します。

許可されるパラメーターの詳細については、「[WINDOWS DEFENDER WMIv2 API」を](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)参照してください。

> [!TIP]
> 他のプラットフォームのウイルス対策関連情報を探している場合は、次を参照してください。
> - [macOS でMicrosoft Defender for Endpointの基本設定を設定する](mac-preferences.md)
> - [Mac 用 Microsoft Defender for Endpoint](microsoft-defender-endpoint-mac.md)
> - [IntuneのMicrosoft Defender ウイルス対策の macOS ウイルス対策ポリシー設定](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [Linux でMicrosoft Defender for Endpointの基本設定を設定する](linux-preferences.md)
> - [Linux 用 Microsoft Defender for Endpoint](microsoft-defender-endpoint-linux.md)
> - [Android の機能で Defender for Endpoint を構成する](android-configure.md)
> - [iOS 機能でMicrosoft Defender for Endpointを構成する](ios-configure-features.md)