---
title: Windows Server 上の Microsoft Defender ウイルス対策
description: サーバー 2019 およびサーバー 2019 でMicrosoft Defender ウイルス対策をWindows Server 2016およびWindowsする方法について学習します。
keywords: windows defender, server, scep, system center endpoint protection, server 2016, current branch, server 2012
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.reviewer: pahuijbr, shwjha
manager: dansimp
ms.technology: mde
ms.topic: article
ms.date: 04/23/2021
ms.openlocfilehash: 175b06738b8c1508dab68c1e19648aa5385a7137
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2021
ms.locfileid: "52269494"
---
# <a name="microsoft-defender-antivirus-on-windows-server"></a>Windows Server 上の Microsoft Defender ウイルス対策

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**

- [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)

Microsoft Defender ウイルス対策サーバーの次のエディション/バージョンでWindowsできます。
- Windows Server 2019
- Windowsサーバー、バージョン 1803 以降
- Windows Server 2016。 

一部のインスタンスでは、Microsoft Defender ウイルス対策と *呼ばれる* Endpoint Protection。ただし、保護エンジンは同じです。 Windows 10 の Microsoft Defender ウイルス対策 では、機能、構成、および管理が大きく同じです[が](microsoft-defender-antivirus-in-windows-10.md)、Windows Server にはいくつかの主な違いがあります。

- サーバー [Windows、定義済](configure-server-exclusions-microsoft-defender-antivirus.md)みのサーバーの役割に基づいて自動除外が適用されます。
 
- サーバー Windows Microsoft 以外のウイルス対策/マルウェア対策ソリューションを実行している場合、Microsoft Defender ウイルス対策はパッシブ モードまたは無効モードに自動的には入りません。 ただし、手動でパッシブ モードMicrosoft Defender ウイルス対策無効モードに設定できます。

## <a name="setting-up-microsoft-defender-antivirus-on-windows-server"></a>サーバーでのMicrosoft Defender ウイルス対策のWindows設定

サーバー プラットフォームでサーバー をセットアップして実行Microsoft Defender ウイルス対策には、いくつかの手順が含まれます。

1. [インターフェイスを有効にします](#enable-the-user-interface-on-windows-server)。
2. [インストールMicrosoft Defender ウイルス対策.](#install-microsoft-defender-antivirus-on-windows-server)
3. [実行中Microsoft Defender ウイルス対策を確認します](#verify-microsoft-defender-antivirus-is-running)。
4. [マルウェア対策のセキュリティ インテリジェンスを更新します](#update-antimalware-security-intelligence)。
5. (必要に応じて) [サンプルを送信します](#submit-samples)。
6. (必要に応じて) [自動除外を構成します](#configure-automatic-exclusions)。
7. (必要な場合のみ)[パッシブ Microsoft Defender ウイルス対策に設定します](#need-to-set-microsoft-defender-antivirus-to-passive-mode)。

## <a name="enable-the-user-interface-on-windows-server"></a>サーバーでユーザー インターフェイスをWindowsする

既定では、Microsoft Defender ウイルス対策サーバーにインストールされ、Windows機能します。 場合によっては、ユーザー インターフェイス (GUI) が既定でインストールされますが、GUI は必要ありません。 PowerShell、グループ ポリシー、または他のメソッドを使用して、ユーザーのMicrosoft Defender ウイルス対策。 

GUI がサーバーにインストールされていない場合にインストールする場合は、役割と機能の追加ウィザードまたは PowerShell コマンドレットを使用します。

### <a name="turn-on-the-gui-using-the-add-roles-and-features-wizard"></a>次のコマンドを使用して GUI を有効役割と機能の追加ウィザード

1. 「[役割と機能の追加ウィザードを](/windows-server/administration/server-manager/install-or-uninstall-roles-role-services-or-features#install-roles-role-services-and-features-by-using-the-add-roles-and-features-wizard)使用して役割、役割サービス、および機能をインストールする」を参照し、次の **役割と機能の追加ウィザード。**

2. ウィザードの [機能]**ステップに** 進み、[機能] の下の [Windows Defender] の **[GUI] オプションをWindows Defender** します。

   この **Windows Server 2016、役割と機能の追加ウィザード** 次のように表示されます。

   ![[役割と機能の追加] オプションの GUI を表示Windows Defenderする](images/server-add-gui.png)

   このWindowsサーバー 2019 では、役割と機能の追加 **ウィザードも** 同様です。

### <a name="turn-on-the-gui-using-powershell"></a>PowerShell を使用して GUI を有効にする

次の PowerShell コマンドレットを使用すると、インターフェイスが有効になります。 

```PowerShell
Install-WindowsFeature -Name Windows-Defender-GUI
```

## <a name="install-microsoft-defender-antivirus-on-windows-server"></a>サーバー Microsoft Defender ウイルス対策インストールWindowsする

サーバーにインストールまたは再インストールする必要があるMicrosoft Defender ウイルス対策、Windowsまたは PowerShell を使用役割と機能の追加ウィザードできます。 

### <a name="use-the-add-roles-and-features-wizard-to-install-microsoft-defender-antivirus"></a>インストールするには、役割と機能の追加ウィザードを使用Microsoft Defender ウイルス対策

1. この記事 [を参照し](/windows-server/administration/server-manager/install-or-uninstall-roles-role-services-or-features#install-roles-role-services-and-features-by-using-the-add-roles-and-features-wizard)、次の **役割と機能の追加ウィザード。**

2. ウィザードの [機能]**ステップに** アクセスしたら、[オプション] Microsoft Defender ウイルス対策します。 また、ユーザー設定 **オプションの GUI Windows Defender** します。

### <a name="use-powershell-to-install-microsoft-defender-antivirus"></a>PowerShell を使用してインストールMicrosoft Defender ウイルス対策

PowerShell を使用してサーバーをインストールMicrosoft Defender ウイルス対策、次のコマンドレットを実行します。

```PowerShell
Install-WindowsFeature -Name Windows-Defender
```

Microsoft Defender AV イベントには、Microsoft Defender ウイルス対策マルウェア対策エンジンのイベント[メッセージが表示されます](troubleshoot-microsoft-defender-antivirus.md)。


## <a name="verify-microsoft-defender-antivirus-is-running"></a>実行中Microsoft Defender ウイルス対策確認する

インストールMicrosoft Defender ウイルス対策、次の手順は、実行されていることを確認します。 サーバー エンドポイントWindows、次の PowerShell コマンドレットを実行します。

```PowerShell
Get-Service -Name windefend
```

ファイアウォール保護が有効になっていることを確認するには、次の PowerShell コマンドレットを実行します。

```PowerShell 
Get-Service -Name mpssvc
```

PowerShell の代わりに、コマンド プロンプトを使用して、コマンド プロンプトMicrosoft Defender ウイルス対策確認できます。 これを行うには、コマンド プロンプトから次のコマンドを実行します。 

```console
sc query Windefend
```

この `sc query` コマンドは、サービスに関する情報Microsoft Defender ウイルス対策します。 このMicrosoft Defender ウイルス対策すると、値が `STATE` 表示されます `RUNNING` 。

## <a name="update-antimalware-security-intelligence"></a>マルウェア対策セキュリティ インテリジェンスの更新 

更新されたマルウェア対策セキュリティ インテリジェンスを取得するには、Update サービスを実行Windows必要があります。 Windows Server Update Services (WSUS) などの更新プログラム管理サービスを使用する場合は、Microsoft Defender ウイルス対策 セキュリティ インテリジェンスの更新プログラムが管理するコンピューターに対して承認されている必要があります。

既定では、Windows更新プログラムは、サーバー 2019 またはサーバー 2019 または Windowsに更新プログラムを自動的にダウンロードWindows Server 2016。 この構成は、次のいずれかの方法で変更できます。


|メソッド  |説明  |
|---------|---------|
|**Windowsの更新** プログラム     |- **更新プログラムをインストールすると**、セキュリティ インテリジェンスの更新プログラムを含むすべての更新Windows Defender自動的にインストールされます。 <br/>- **更新プログラムをダウンロードします** が、セキュリティ インテリジェンス更新プログラムを自動的にダウンロードWindows Defenderインストールできるかどうかを選択しますが、他の更新プログラムは自動的にインストールされません。       |
|**グループ ポリシー**     | グループ ポリシーで使用可能な設定を使用して、Windows Update をセットアップおよび管理できます。管理用テンプレート **\Windows コンポーネント\Windows Update\Configure 自動更新**         |
|**AUOptions** レジストリ キー     |次の 2 つの値を使用するとWindowsセキュリティ インテリジェンス更新プログラムを自動的にダウンロードしてインストールできます。 <br/>- **4**  - **更新プログラムを自動的にインストールします**。 この値を指定すると、セキュリティ インテリジェンス更新プログラムを含むすべての更新Windows Defender自動的にインストールされます。 <br/>- **3**  - **更新プログラムをダウンロードしますが、インストールするかどうかを選択します**。  この値を使用Windows Defenderセキュリティ インテリジェンス更新プログラムを自動的にダウンロードしてインストールできますが、他の更新プログラムは自動的にインストールされません。         |

マルウェアからの保護を確実に維持するには、次のサービスを有効にすることをお勧めします。

- Windows エラー報告 サービス

- Windowsサービスの更新

次の表に、サービスと依存Microsoft Defender ウイルス対策サービスの一覧を示します。

|サービス名|ファイルの場所|説明|
|--------|---------|--------|
|Windows Defenderサービス (WinDefend)|`C:\Program Files\Windows Defender\MsMpEng.exe`|これは、Microsoft Defender ウイルス対策実行する必要がある主要なサービスです。|
|Windows エラー報告サービス (Wersvc)|`C:\WINDOWS\System32\svchost.exe -k WerSvcGroup`|このサービスは、エラー レポートを Microsoft に返します。|
|Windows Defender ファイアウォール (MpsSvc)|`C:\WINDOWS\system32\svchost.exe -k LocalServiceNoNetwork`|サービスを有効にWindows Defender ファイアウォールすることをお勧めします。|
|Windows更新プログラム (Wuauserv)|`C:\WINDOWS\system32\svchost.exe -k netsvcs`|Windowsセキュリティ インテリジェンスの更新プログラムとマルウェア対策エンジンの更新プログラムを取得するには、更新プログラムが必要です|

## <a name="submit-samples"></a>サンプルの送信

サンプル提出により、Microsoft は悪意のある可能性のあるソフトウェアのサンプルを収集できます。 Microsoft の研究者は、継続的で最新の保護を提供するために、これらのサンプルを使用して疑わしいアクティビティを分析し、更新されたマルウェア対策セキュリティ インテリジェンスを生成します。 プログラムの実行可能ファイル (ファイルやファイル.exeなど) を.dllします。 ドキュメントや PDF ファイルなど、個人データを含むMicrosoft Word収集は行います。

### <a name="submit-a-file"></a>ファイルを送信する

1. 申請ガイド [を確認します](/windows/security/threat-protection/intelligence/submission-guide)。

2. サンプル提出 [ポータルにアクセスし](https://www.microsoft.com/wdsi/filesubmission)、ファイルを提出します。


### <a name="enable-automatic-sample-submission"></a>自動サンプル申請を有効にする

自動サンプル送信を有効にするには、管理者として Windows PowerShell コンソールを起動し、次のいずれかの設定に従って **SubmitSamplesConsent** 値データを設定します。

|Setting  |説明  |
|---------|---------|
|**0**  - **常にプロンプトを表示する**     |サービスMicrosoft Defender ウイルス対策、必要なすべてのファイルの提出を確認するように求めるメッセージが表示されます。 この設定は、Microsoft Defender ウイルス対策の既定の設定ですが、GUI を使用しない Windows Server 2016または 2019 のインストールには推奨されません。         |
|**1**   - **安全なサンプルを自動的に送信する**     |Microsoft Defender ウイルス対策サービスは、"セーフ" とマークされたファイルを送信し、残りのファイルを求めるメッセージを表示します。         |
|**2**  - **送信しない**      |Microsoft Defender ウイルス対策サービスはプロンプトを表示しないし、ファイルも送信しない。         |
|**3**  - **すべてのサンプルを自動的に送信する**     |Microsoft Defender ウイルス対策サービスは、確認を求めるメッセージを表示せずにすべてのファイルを送信します。         |

## <a name="configure-automatic-exclusions"></a>自動除外を構成する

セキュリティとパフォーマンスを確保するために、特定の除外は、Microsoft Defender ウイルス対策 または 2019 の Windows Server 2016 を使用するときにインストールする役割と機能に基づいて自動的に追加されます。

「Configure [exclusions in Microsoft Defender ウイルス対策 on Windows」 を参照してください](configure-server-exclusions-microsoft-defender-antivirus.md)。 

## <a name="need-to-set-microsoft-defender-antivirus-to-passive-mode"></a>パッシブ モードにMicrosoft Defender ウイルス対策する必要がありますか?

Windows Server で Microsoft 以外のウイルス対策製品をプライマリ ウイルス対策ソリューションとして使用している場合は、Microsoft Defender ウイルス対策モードまたは無効モードに設定する必要があります。

- サーバー Windowsバージョン 1803 以降、または Windows Server 2019 では、Microsoft Defender ウイルス対策パッシブ モードに設定できます。  

- このWindows Server 2016、Microsoft Defender ウイルス対策 Microsoft 以外のウイルス対策/マルウェア対策製品と共にサポートされていません。 このような場合は、無効モードにMicrosoft Defender ウイルス対策する必要があります。

### <a name="set-microsoft-defender-antivirus-to-passive-mode-using-powershell"></a>PowerShell をMicrosoft Defender ウイルス対策パッシブ モードに設定する

Windows Server バージョン 1803 または Windows Server 2019 を使用している場合は、次の PowerShell コマンドレットを使用して Microsoft Defender ウイルス対策 をパッシブ モードに設定できます。

`CMDLET NEEDED`

### <a name="set-microsoft-defender-antivirus-to-passive-mode-using-group-policy"></a>グループ Microsoft Defender ウイルス対策を使用してパッシブ モードに設定する

プロシージャが必要

### <a name="set-microsoft-defender-antivirus-to-passive-mode-using-a-registry-key"></a>レジストリ Microsoft Defender ウイルス対策を使用してパッシブ モードに設定する

Windows Server バージョン 1803 または Windows Server 2019 を使用している場合は、次のレジストリ キーを設定して、Microsoft Defender ウイルス対策 をパッシブ モードに設定できます。
- パス: `HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`
- 名前: `ForceDefenderPassiveMode`
- タイプ: `REG_DWORD`
- 値: `1`

### <a name="disable-microsoft-defender-antivirus-using-the-remove-roles-and-features-wizard"></a>[役割Microsoft Defender ウイルス対策機能の削除] ウィザードを使用して無効にする

1. 「 [役割、役割サービス、または機能のインストール](/windows-server/administration/server-manager/install-or-uninstall-roles-role-services-or-features#remove-roles-role-services-and-features-by-using-the-remove-roles-and-features-wizard)またはアンインストール」を参照し、役割と機能の削除 **ウィザードを使用します**。 

2. ウィザードの [機能]**ステップに** アクセスしたら、[機能] オプションWindows Defender **解除** します。 

    [**機能Windows Defender]** セクションでWindows Defenderをオフにすると、インターフェイス オプション **の GUI** を削除するように求Windows Defender。 
    
    Microsoft Defender ウイルス対策インターフェイスなしでは正常に実行されますが、コア インターフェイス機能を無効にした場合、ユーザー **インターフェイスWindows Defender** できません。

### <a name="turn-off-the-microsoft-defender-antivirus-user-interface-using-powershell"></a>PowerShell を使用Microsoft Defender ウイルス対策ユーザー インターフェイスをオフにする

GUI をオフMicrosoft Defender ウイルス対策、次の PowerShell コマンドレットを使用します。

```PowerShell
Uninstall-WindowsFeature -Name Windows-Defender-GUI
```

### <a name="are-you-using-windows-server-2016"></a>アプリを使用Windows Server 2016?

microsoft によって提供または開発されていない Windows Server 2016 およびサード パーティ製のマルウェア対策/ウイルス対策製品を使用している場合は、Microsoft Defender ウイルス対策 を無効またはアンインストールする必要があります。 

> [!NOTE]
> アプリをアンインストールWindows セキュリティ、これらの手順でインターフェイスを無効にできます。

次の PowerShell コマンドレットは、Microsoft Defender ウイルス対策をWindows Server 2016。

```PowerShell
Uninstall-WindowsFeature -Name Windows-Defender
```

サーバーでMicrosoft Defender ウイルス対策をWindows Server 2016するには、次の PowerShell コマンドレットを使用します。

```PowerShell
Set-MpPreference -DisableRealtimeMonitoring $true
```

## <a name="see-also"></a>関連項目

- [Microsoft Defender ウイルス対策 (Windows 10)](microsoft-defender-antivirus-in-windows-10.md)
- [Microsoft Defender ウイルス対策互換性](microsoft-defender-antivirus-compatibility.md)
