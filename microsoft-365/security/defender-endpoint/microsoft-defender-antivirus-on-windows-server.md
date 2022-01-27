---
title: Windows Server 上の Microsoft Defender ウイルス対策
description: サーバー 2019、Microsoft Defender ウイルス対策サーバー 2019、Windows Server 2016 Windowsサーバー 2022 Windows構成する方法について学習します。
keywords: Windows Defender、サーバー、scep、System Center Endpoint 保護、Server 2016、Current Branch、Server 2012
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.reviewer: pahuijbr, shwjha
manager: dansimp
ms.technology: mde
ms.topic: article
ms.date: 01/26/2022
ms.collection:
- M365-security-compliance
- m365initiative-defender-endpoint
ms.openlocfilehash: 0ea2184720467b3756b5cde8c8973e8952d5b50c
ms.sourcegitcommit: aac7e002ec6e10a41baa2d0bd38614b0ed471a70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/27/2022
ms.locfileid: "62244705"
---
# <a name="microsoft-defender-antivirus-on-windows-server"></a>Windows Server 上の Microsoft Defender ウイルス対策

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

Microsoft Defender ウイルス対策サーバーの次のエディション/バージョンでWindowsできます。

- Windows Server 2022
- Windows Server 2019
- Windows Server バージョン 1803 以降
- Windows Server 2016
- Windows Server 2012 R2 (エンドポイントに Microsoft Defender が必要)

場合によっては、Microsoft Defender ウイルス対策は *Endpoint Protection* と呼ばることもありますが、保護エンジンは同じです。 Windows 10 および Windows 11 の Microsoft Defender ウイルス対策 の機能、構成、および管理は大きく同じですが[、Windows](microsoft-defender-antivirus-windows.md) Server にはいくつかの主な違いがあります。

- Windows Server では、[自動除外](configure-server-exclusions-microsoft-defender-antivirus.md) が定義によるサーバー ロールに基づいて適用されます。

- Windows サーバーで、Microsoft 以外のウイルス対策/マルウェア対策ソリューションを実行している場合、Microsoft Defender ウイルス対策 はパッシブ モードまたは無効モードに自動的には入りません。 ただし、Microsoft Defender ウイルス対策を手動でパッシブ モードまたは無効モードに設定できます。

## <a name="setting-up-microsoft-defender-antivirus-on-windows-server"></a>Windows Server 上の Microsoft Defender ウイルス対策の設定

サーバー プラットフォームで Microsoft Defender ウイルス対策を設定して実行するプロセスには、いくつかの手順があります:

1. [インターフェイスを有効にします](#enable-the-user-interface-on-windows-server)。
2. [Microsoft Defender ウイルス対策をインストールします](#install-microsoft-defender-antivirus-on-windows-server)。
3. [実行中の Microsoft Defender を確認します](#verify-microsoft-defender-antivirus-is-running)。
4. [マルウェア対策セキュリティ インテリジェンスを更新します](#update-antimalware-security-intelligence)。
5. (必要に応じて) [サンプルを送信します](#submit-samples)。
6. (必要に応じて) [自動除外を構成します](#configure-automatic-exclusions)。
7. (必要な場合のみ)サーバー [Windowsパッシブ モードに設定します](#passive-mode-and-windows-server)。

## <a name="enable-the-user-interface-on-windows-server"></a>Windows Server でユーザー インターフェイスを有効にする

既定では、Microsoft Defender ウイルス対策が Windows Server にインストールされており機能することになっています。 場合によっては、ユーザー インターフェイス (GUI) が既定でインストールされますが、GUI は必要ありません。 PowerShell、グループ ポリシー、またはその他のメソッドを使用して、Microsoft Defender ウイルス対策を管理できます。

GUI がサーバーにインストールされていない場合にインストールする場合は、役割と機能の追加ウィザードまたは PowerShell コマンドレットを使用します。

> [!NOTE]
> このオプションは、R2 のWindows Server 2012できません。 詳細については [、「Options to install Microsoft Defender for Endpoint」を参照してください](configure-server-endpoints.md#options-to-install-the-microsoft-defender-for-endpoint-packages)。

### <a name="turn-on-the-gui-using-the-add-roles-and-features-wizard"></a>役割と機能の追加ウィザードを使用して GUI を有効にする

1. [役割と機能の追加ウィザードを使用して役割、役割サービス、および機能をインストールする](/windows-server/administration/server-manager/install-or-uninstall-roles-role-services-or-features#install-roles-role-services-and-features-by-using-the-add-roles-and-features-wizard) を参照してから、**役割と機能の追加ウィザード** を使用します。

2. ウィザードの **機能** ステップにアクセスし、**Windows Defender 機能** で **Windows Defender 用 GUI** オプションを選択します。

   Windows Server 2016 では、**役割と機能の追加ウィザード** は次のように表示されます。

   ![[ユーザー設定] オプションの GUI を示す役割とWindows Defender追加します。](images/server-add-gui.png)

   サーバー 2019 Windowsサーバー 2022 Windows役割と機能の追加 **ウィザードは** 似ています。

### <a name="turn-on-the-gui-using-powershell"></a>PowerShell を使用して GUI を有効にする

次の PowerShell コマンドレットを使用すると、インターフェイスが有効になります。

```powershell
Install-WindowsFeature -Name Windows-Defender-GUI
```

## <a name="install-microsoft-defender-antivirus-on-windows-server"></a>Windows Server 上の Microsoft Defender ウイルス対策をインストールする

Windows Server に Microsoft Defender ウイルス対策をインストールまたは再インストールする必要がある場合は、**役割と機能の追加ウィザード** または PowerShell を使用してインストールできます。

### <a name="use-the-add-roles-and-features-wizard-to-install-microsoft-defender-antivirus"></a>役割と機能の追加ウィザードを使用して Microsoft Defender ウイルス対策をインストールする

1. [この記事](/windows-server/administration/server-manager/install-or-uninstall-roles-role-services-or-features#install-roles-role-services-and-features-by-using-the-add-roles-and-features-wizard)を参照してから、**役割と機能の追加ウィザード** を使用します。

2. ウィザードの **機能** ステップにアクセスし、Microsoft Defender ウイルス対策オプションを選択します。 **Windows Defender 用 GUI** オプションも選択します。

### <a name="use-powershell-to-install-microsoft-defender-antivirus"></a>PowerShell を使用して Microsoft Defender ウイルス対策をインストールする

PowerShell を使用して Microsoft Defender ウイルス対策をインストールするには、次のコマンドレットを実行します。

```powershell
Install-WindowsFeature -Name Windows-Defender
```

マルウェア対策エンジンのイベント メッセージは、Microsoft Defender ウイルス対策 イベント[にMicrosoft Defender ウイルス対策できます](troubleshoot-microsoft-defender-antivirus.md)。

## <a name="verify-microsoft-defender-antivirus-is-running"></a>実行中の Microsoft Defender を確認する

Microsoft Defender ウイルス対策をインストールしたら、次のステップで実行できることを確認します。 Windows Server エンドポイントで、次の PowerShell コマンドレットを実行します。

```powershell
Get-Service -Name windefend
```

ファイアウォール保護が有効になっていることを確認するには、次の PowerShell コマンドレットを実行します。

```powershell
Get-Service -Name mpssvc
```

PowerShell の代わりに、コマンド プロンプトを使用して、Microsoft Defender ウイルス対策が実行できることを確認できます。 これを行うには、コマンド プロンプトで次のコマンドを実行します。

```console
sc query Windefend
```

`sc query` コマンドは、Microsoft Defender ウイルス対策 サービスに関する情報を返します。 Microsoft Defender ウイルス対策を実行中は、`STATE` の値に `RUNNING`が表示されます。

実行されていないすべてのサービスを表示するには、次の PowerShell コマンドレットを実行します。

```console
sc query state= all
```

## <a name="update-antimalware-security-intelligence"></a>マルウェア対策セキュリティ インテリジェンスを更新する

更新されたマルウェア対策セキュリティ インテリジェンスを取得するには、Windows Update サービスを実装する必要があります。 Windows Server Update Services (WSUS) などの更新管理サービスを使用する場合は、Microsoft Defender ウイルス対策 セキュリティ インテリジェンスへの更新プログラムが管理するコンピューターに対して承認されていることを確認します。

既定では、Windows Update は Windows Server 2019 または Windows Server 2022 または Windows Server 2016 に更新プログラムを自動的にダウンロードおよびインストールしません。 この構成を変更するには、以下のいずれかの方法を使用します。

<br/><br/>

| メソッド | 説明 |
|---|---|
| コントロール パネルにある **Windows Update** | **更新プログラムを自動的にインストールする** と、Windows Defender セキュリティ インテリジェンス更新プログラムを含むすべての更新プログラムが自動的にインストールされます。 <br/><br/> **更新プログラムをダウンロードします** が、セキュリティ インテリジェンス更新プログラムをWindows Defenderインストールできるかどうかを選択しますが、他の更新プログラムは自動的にインストールされません。 |
| **グループ ポリシー** | 次のパスでグループ ポリシー内で使用できる設定を利用して、Windows Updateを設定、管理できます: **Administrative Templates\Windows Components\Windows Update\Configure Automatic Updates** |
| **AUOptions** レジストリ キー | 次の 2 つの値を使用すると、Windows Update でセキュリティ インテリジェンス更新プログラムを自動的にダウンロードしてインストールできます。 <br/><br/> **4** - **更新プログラムを自動的にインストールします**。 この値を使用すると、Windows Defender セキュリティ インテリジェンス更新プログラムを含むすべての更新プログラムを自動的にインストールできます。 <br/><br/> **3** - **更新プログラムをダウンロードし、自分でインストールを決定します**。 この値を使用Windows Defenderセキュリティ インテリジェンス更新プログラムを自動的にダウンロードしてインストールできますが、他の更新プログラムは自動的にインストールされません。 |

マルウェアからの保護を維持できるようにするには、次のサービスを有効にすることをお勧めします。

- Windows エラー報告サービス
- Windows Update サービス

次の表は、Microsoft Defender ウイルス対策のサービスと依存サービスの一覧です。

<br/><br/>


| サービス名 | [ファイルの場所] | 説明 |
|---|---|---|
| Windows Defender サービス (WinDefend) | `C:\Program Files\Windows Defender\MsMpEng.exe` | これは、常に実行する必要がある主な Microsoft Defender ウイルス対策 サービスです。|
| Windows エラー報告サービス (Wersvc) | `C:\WINDOWS\System32\svchost.exe -k WerSvcGroup` | このサービスは、エラー レポートを Microsoft に返送します。 |
| Windows Defender ファイアウォール (MpsSvc) | `C:\WINDOWS\system32\svchost.exe -k LocalServiceNoNetwork` | Windows Defender ファイアウォール サービスは有効のままにしておくことをお勧めします。 |
| Windows Update (Wuauserv) | `C:\WINDOWS\system32\svchost.exe -k netsvcs`| セキュリティ インテリジェンスの更新プログラムとマルウェア対策エンジンの更新プログラムを取得するには、Windows Update が必要です |

## <a name="submit-samples"></a>サンプルを送信する

サンプルの送信で、Microsoft が悪意のある可能性のあるソフトウェアのサンプルを収集できるようになります。 継続的かつ最新の保護を提供できるように、Microsoft 専門家がこれらのサンプルを使用して疑わしいアクティビティを分析し、マルウェア対策セキュリティ インテリジェンスの更新プログラムを生成しています。 Microsoft では.exe ファイルや .dll ファイルなどのプログラム実行可能ファイルを収集しています。 ドキュメントや PDF ファイルなど、個人データを含むMicrosoft Word収集する必要があります。

### <a name="submit-a-file"></a>ファイルを送信する

1. [送信ガイド](/windows/security/threat-protection/intelligence/submission-guide) を確認します。
2. [サンプル送信ポータル](https://www.microsoft.com/wdsi/filesubmission)にアクセスし、ファイルを送信します。

### <a name="enable-automatic-sample-submission"></a>サンプルの自動送信を有効にする

サンプルの自動送信を有効にするには、管理者として Windows PowerShell コンソールを起動し、次のいずれかの設定に従って **SubmitSamplesConsent** 値データを設定します。

<br/><br/>

|Setting|説明|
|---|---|
| **0** - **常にプロンプトを表示する** | Microsoft Defender ウイルス対策 サービスで、必要なすべてのファイルの送信を確認するプロンプトが表示されます。 これは Microsoft Defender ウイルス対策 の既定の設定ですが、Windows Server 2016 または 2019、または Windows Server 2022 のインストールでは GUI を使用しない場合は推奨されません。 |
| **1**  - **安全なサンプルを自動的に送信する** | Microsoft Defender ウイルス対策 サービスで "安全" とマークされたすべてのファイルが送信され、その他のファイルにはプロンプトが表示されます。 |
| **2** - **送信しない** | Microsoft Defender ウイルス対策サービスはプロンプトを表示しないし、ファイルも送信しない。 |
| **3** - **すべてのサンプルを自動的に送信する** | Microsoft Defender ウイルス対策 サービスでは確認を行うプロンプトが表示されず、すべてのファイルが送信されます。 |

> [!NOTE]
> このオプションは、R2 のWindows Server 2012できません。 


## <a name="configure-automatic-exclusions"></a>自動除外を構成する

セキュリティとパフォーマンスを確保するために、Microsoft Defender ウイルス対策 on Windows Server 2016 または 2019、または Windows Server 2022 を使用するときにインストールする役割と機能に基づいて、特定の除外が自動的に追加されます。

詳細については、「[Windows Server 上の Microsoft Defender ウイルス対策で除外を構成する](configure-server-exclusions-microsoft-defender-antivirus.md)」を参照してください。

## <a name="passive-mode-and-windows-server"></a>パッシブ モードと Windows サーバー

Windows Server で Microsoft 以外のウイルス対策製品をプライマリ ウイルス対策ソリューションとして使用している場合は、Microsoft Defender ウイルス対策モードまたは無効モードに設定する必要があります。

詳細については、「Install [Microsoft Defender ウイルス対策 on Windows」を参照してください](microsoft-defender-antivirus-on-windows-server.md#install-microsoft-defender-antivirus-on-windows-server)。


### <a name="set-microsoft-defender-antivirus-to-passive-mode-using-a-registry-key"></a>レジストリ キーを使用して Microsoft Defender ウイルス対策をパッシブ モードに設定する

次のレジストリ Microsoft Defender ウイルス対策をパッシブ モードに設定できます。
- パス: `HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`
- 名前: `ForceDefenderPassiveMode`
- 種類`REG_DWORD`
- 値: `1`

### <a name="disable-microsoft-defender-antivirus-using-the-remove-roles-and-features-wizard"></a>役割と機能の削除ウィザードを使用して Microsoft Defender ウイルス対策を無効にする

1. 「[役割のインストールまたはアンインストール、役割サービス、または機能](/windows-server/administration/server-manager/install-or-uninstall-roles-role-services-or-features#remove-roles-role-services-and-features-by-using-the-remove-roles-and-features-wizard)」 を参照してから、**役割と機能の削除ウィザード** を使用します。

2. ウィザードの **機能** ステップにアクセスし、**Windows Defender 機能** オプションを解除します。

    [Windows Defender **Windows Defender** 機能 **]** セクションの下でWindows Defenderをオフにすると、インターフェイス オプション **の GUI** を削除するように求めるメッセージが表示Windows Defender。

    Microsoft Defender ウイルス対策インターフェイスなしでは正常に実行されますが、コア インターフェイス機能を無効にした場合、ユーザー インターフェイス **Windows Defender** できません。

### <a name="turn-off-the-microsoft-defender-antivirus-user-interface-using-powershell"></a>PowerShell を使用して Microsoft Defender ウイルス対策ユーザー インターフェイスをオフにする

Microsoft Defender ウイルス対策 GUI をオフにするには、次の PowerShell コマンドレットを使用します。

```powershell
Uninstall-WindowsFeature -Name Windows-Defender-GUI
```

### <a name="are-you-using-windows-server-2012-r2-or-windows-server-2016"></a>R2 または Windows Server 2012を使用Windows Server 2016?

これで、R2 と Microsoft Defender ウイルス対策のパッシブ モードでWindows Server 2012実行Windows Server 2016。 詳細については [、「Options to install Microsoft Defender for Endpoint」を参照してください](configure-server-endpoints.md#options-to-install-the-microsoft-defender-for-endpoint-packages)。

<br/><br/>

| プロシージャ | 説明 |
|---|---|
| グループ ポリシー Microsoft Defender ウイルス対策使用して無効にする | ローカル グループ ポリシー エディターで、[管理用テンプレート] Windows コンポーネント Endpoint Protectionを無効Endpoint Protectionし、[OK を有効にする  >    >    >  ]**を**  >  **選択します**。 |
| レジストリ Microsoft Defender ウイルス対策を使用して無効にする | [DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware)レジストリ キーを使用するには、に移動し、という DWORD エントリを設定または `HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender` 作成します `DisableAntiSpyware` 。 その値を `1` (レジストリ キーの値を true に設定する) に *設定します*。 |
| PowerShell をMicrosoft Defender ウイルス対策する方法を無効にする | 次の PowerShell コマンドレットを使用します。 `Set-MpPreference -DisableRealtimeMonitoring $true` |
| PowerShell をMicrosoft Defender ウイルス対策をアンインストールする | 次の PowerShell コマンドレットを使用します。 `Uninstall-WindowsFeature -Name Windows-Defender` |


## <a name="see-also"></a>関連項目

- [Windows の Microsoft Defender ウイルス対策](microsoft-defender-antivirus-windows.md)
- [Microsoft Defender ウイルス対策互換性](microsoft-defender-antivirus-compatibility.md)
