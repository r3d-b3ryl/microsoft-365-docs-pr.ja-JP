---
title: Windows Server 上の Microsoft Defender ウイルス対策
description: Server 2016、Windows Server 2019、および Windows Server 2022 上のMicrosoft Defender ウイルス対策を有効にして構成する方法について説明します。
keywords: Windows Defender、サーバー、scep、System Center Endpoint 保護、Server 2016、Current Branch、Server 2012
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.reviewer: pahuijbr
manager: dansimp
ms.technology: mde
ms.topic: article
ms.date: 04/01/2022
ms.collection:
- M365-security-compliance
- m365initiative-defender-endpoint
ms.openlocfilehash: b93595375982e3ed61d1ac94ae410575b0d72307
ms.sourcegitcommit: 85ce5fd0698b6f00ea1ea189634588d00ea13508
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/06/2022
ms.locfileid: "64666990"
---
# <a name="microsoft-defender-antivirus-on-windows-server"></a>Windows Server 上の Microsoft Defender ウイルス対策

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

Microsoft Defender ウイルス対策は、次のエディション/バージョンの Windows Server で利用できます。

- Windows Server 2022
- Windows Server 2019
- Windows Server バージョン 1803 以降
- Windows Server 2016
- Windows Server 2012 R2 (Microsoft Defender for Endpoint が必要)

## <a name="setting-up-microsoft-defender-antivirus-on-windows-server"></a>Windows Server 上の Microsoft Defender ウイルス対策の設定

Windows Server でMicrosoft Defender ウイルス対策を設定して実行するプロセスには、次の手順が含まれます。

1. [インターフェイスを有効にします](#enable-the-user-interface-on-windows-server)。
2. [Microsoft Defender ウイルス対策をインストールします](#install-microsoft-defender-antivirus-on-windows-server)。
3. [実行中の Microsoft Defender を確認します](#verify-microsoft-defender-antivirus-is-running)。
4. [マルウェア対策セキュリティ インテリジェンスを更新します](#update-antimalware-security-intelligence)。
5. (必要に応じて) [サンプルを送信します](#submit-samples)。
6. (必要に応じて) [自動除外を構成します](#configure-automatic-exclusions)。
7. (必要な場合のみ) [Windows Server をパッシブ モード](#passive-mode-and-windows-server) を設定します。

## <a name="enable-the-user-interface-on-windows-server"></a>Windows Server でユーザー インターフェイスを有効にする

> [!IMPORTANT]
> Windows Server 2012 R2 を使用している場合は、「[Microsoft Defender for Endpointをインストールするオプション」を](configure-server-endpoints.md#options-to-install-the-microsoft-defender-for-endpoint-packages)参照してください。

既定では、Microsoft Defender ウイルス対策が Windows Server にインストールされており機能することになっています。 場合によっては、ユーザー インターフェイス (GUI) が既定でインストールされます。 GUI は必要ありません。PowerShell、グループ ポリシー、またはその他の方法を使用して、Microsoft Defender ウイルス対策を管理できます。 ただし、多くの組織では、Microsoft Defender ウイルス対策に GUI を使用することを好みます。 GUI をインストールするには、次の表のいずれかの手順を使用します。

| プロシージャ | 操作 |
|:---|:---|
| 役割と機能の追加ウィザードを使用して GUI を有効にする | 1. [ロールと機能の追加ウィザードを使用してロール、役割サービス、機能をインストールする方法と、ロールと機能](/windows-server/administration/server-manager/install-or-uninstall-roles-role-services-or-features#install-roles-role-services-and-features-by-using-the-add-roles-and-features-wizard)の **追加ウィザード** を使用する方法に関するページを参照してください。 <br/><br/>2. ウィザードの **[機能**] ステップにアクセスしたら、[**Windows Defender機能**] で [**Windows Defenderオプションの GUI** を選択します。 |
| PowerShell を使用して GUI を有効にする | 1. Windows サーバーで、管理者としてWindows PowerShellを開きます。 <br/><br/>2. 次の PowerShell コマンドレットを実行します。 `Install-WindowsFeature -Name Windows-Defender-GUI` |

## <a name="install-microsoft-defender-antivirus-on-windows-server"></a>Windows Server 上の Microsoft Defender ウイルス対策をインストールする

Windows Server にMicrosoft Defender ウイルス対策をインストールまたは再インストールする必要がある場合は、次の表のいずれかの手順を使用します。

| プロシージャ | 操作 |
|:---|:---|
| 役割と機能の追加ウィザードを使用して Microsoft Defender ウイルス対策をインストールする | 1. [ロール、役割サービス、または機能のインストールまたはアンインストールに](/windows-server/administration/server-manager/install-or-uninstall-roles-role-services-or-features#install-roles-role-services-and-features-by-using-the-add-roles-and-features-wizard)関するページを参照し、 **ロールと機能の追加ウィザード** を使用します。 <br/><br/>2. ウィザードの **[機能**] ステップにアクセスしたら、Microsoft Defender ウイルス対策 オプションを選択します。 **Windows Defender 用 GUI** オプションも選択します。 |
| PowerShell を使用して Microsoft Defender ウイルス対策をインストールする | 1. Windows サーバーで、管理者としてWindows PowerShellを開きます。 <br/><br/>2. 次の PowerShell コマンドレットを実行します。 `Install-WindowsFeature -Name Windows-Defender` |

> [!NOTE]
> Microsoft Defender ウイルス対策に含まれるマルウェア対策エンジンのイベント メッセージも、[Microsoft Defender ウイルス対策イベント](troubleshoot-microsoft-defender-antivirus.md) で検出されることがあります。

## <a name="verify-microsoft-defender-antivirus-is-running"></a>実行中の Microsoft Defender を確認する

Microsoft Defender ウイルス対策をインストール (または再インストール) したら、次の手順では、実行されていることを確認します。 次の表の PowerShell コマンドレットを使用します。

| プロシージャ | PowerShell コマンドレット |
|:---|:---|
| Microsoft Defender ウイルス対策が実行されていることを確認する | `Get-Service -Name windefend` |
| ファイアウォール保護が有効になっていることを確認する | `Get-Service -Name mpssvc` |

PowerShell の代わりに、コマンド プロンプトを使用して、Microsoft Defender ウイルス対策が実行できることを確認できます。 これを行うには、コマンド プロンプトで次のコマンドを実行します。

```cmd
sc query Windefend
```

`sc query` コマンドは、Microsoft Defender ウイルス対策 サービスに関する情報を返します。 Microsoft Defender ウイルス対策を実行中は、`STATE` の値に `RUNNING`が表示されます。

実行中でないすべてのサービスを表示するには、次の PowerShell コマンドレットを実行します。

```cmd
sc query state= all
```

## <a name="update-antimalware-security-intelligence"></a>マルウェア対策セキュリティ インテリジェンスを更新する

通常のセキュリティ インテリジェンス更新プログラムを取得するには、Windows Update サービスが実行されている必要があります。 Windows Server Update Services (WSUS) などの更新管理サービスを使用する場合は、Microsoft Defender ウイルス対策 セキュリティ インテリジェンスへの更新プログラムが管理するコンピューターに対して承認されていることを確認します。

既定では、Windows Updateは、Windows Server 2019 または Windows Server 2022 または Windows Server 2016に更新プログラムを自動的にダウンロードしてインストールしません。 この構成を変更するには、以下のいずれかの方法を使用します。

| メソッド | 説明 |
|---|---|
| コントロール パネルにある **Windows Update** | **更新プログラムを自動的にインストールする** と、Windows Defender セキュリティ インテリジェンス更新プログラムを含むすべての更新プログラムが自動的にインストールされます。 <br/><br/> **更新プログラムをダウンロードしますが、インストールするかどうかを選択すると**、セキュリティ インテリジェンス更新プログラムを自動的にダウンロードしてインストールWindows Defenderが、他の更新プログラムは自動的にインストールされません。 |
| **グループ ポリシー** | 次のパスでグループ ポリシー内で使用できる設定を利用して、Windows Updateを設定、管理できます: **Administrative Templates\Windows Components\Windows Update\Configure Automatic Updates** |
| **AUOptions** レジストリ キー | 次の 2 つの値を使用すると、Windows Update でセキュリティ インテリジェンス更新プログラムを自動的にダウンロードしてインストールできます。 <br/><br/> **4** - **更新プログラムを自動的にインストールする**。この値を設定すると、Windows Defender セキュリティ インテリジェンス更新プログラムを含むすべての更新プログラムが自動的にインストールされるようになります。<br/><br/> **3** - **更新プログラムをダウンロードし、自分でインストールを決定します**。 この値を使用するとWindows Defenderセキュリティ インテリジェンス更新プログラムを自動的にダウンロードしてインストールできますが、他の更新プログラムは自動的にインストールされません。 |

マルウェアからの保護を確実に維持するには、次のサービスを有効にします。

- Windows エラー報告サービス
- Windows Update サービス

次の表は、Microsoft Defender ウイルス対策のサービスと依存サービスの一覧です。

| サービス名 | [ファイルの場所] | 説明 |
|---|---|---|
| Windows Defender サービス (WinDefend) | `C:\Program Files\Windows Defender\MsMpEng.exe` | これは、常に実行する必要がある主要なMicrosoft Defender ウイルス対策 サービスです。|
| Windows エラー報告サービス (Wersvc) | `C:\WINDOWS\System32\svchost.exe -k WerSvcGroup` | このサービスは、エラー レポートを Microsoft に返送します。 |
| Windows Defender ファイアウォール (MpsSvc) | `C:\WINDOWS\system32\svchost.exe -k LocalServiceNoNetwork` | Windows Defenderファイアウォール サービスを有効にしておくことをお勧めします。 |
| Windows Update (Wuauserv) | `C:\WINDOWS\system32\svchost.exe -k netsvcs`| セキュリティ インテリジェンスの更新プログラムとマルウェア対策エンジンの更新プログラムを取得するには、Windows Update が必要です |

## <a name="submit-samples"></a>サンプルを送信する

サンプルの送信で、Microsoft が悪意のある可能性のあるソフトウェアのサンプルを収集できるようになります。 継続的かつ最新の保護を提供できるように、Microsoft 専門家がこれらのサンプルを使用して疑わしいアクティビティを分析し、マルウェア対策セキュリティ インテリジェンスの更新プログラムを生成しています。 Microsoft では.exe ファイルや .dll ファイルなどのプログラム実行可能ファイルを収集しています。 Microsoft Wordドキュメントや PDF ファイルなど、個人データを含むファイルは収集されません。

### <a name="submit-a-file"></a>ファイルを送信する

1. [送信ガイド](/windows/security/threat-protection/intelligence/submission-guide) を確認します。

2. [サンプル送信ポータル](https://www.microsoft.com/wdsi/filesubmission)にアクセスし、ファイルを送信します。

### <a name="enable-automatic-sample-submission"></a>サンプルの自動送信を有効にする

サンプルの自動送信を有効にするには、管理者として Windows PowerShell コンソールを起動し、次のいずれかの設定に従って **SubmitSamplesConsent** 値データを設定します。

|Setting|説明|
|---|---|
| **0** - **常にプロンプトを表示する** | Microsoft Defender ウイルス対策 サービスで、必要なすべてのファイルの送信を確認するプロンプトが表示されます。 これはMicrosoft Defender ウイルス対策の既定の設定ですが、Windows Server 2016または 2019 のインストール、または GUI を使用しないサーバー 2022 のWindowsには推奨されません。 |
| **1**  - **安全なサンプルを自動的に送信する** | Microsoft Defender ウイルス対策 サービスで "安全" とマークされたすべてのファイルが送信され、その他のファイルにはプロンプトが表示されます。 |
| **2** - **送信しない** | Microsoft Defender ウイルス対策 サービスはメッセージを表示せず、ファイルを送信しません。 |
| **3** - **すべてのサンプルを自動的に送信する** | Microsoft Defender ウイルス対策 サービスでは確認を行うプロンプトが表示されず、すべてのファイルが送信されます。 |

> [!NOTE]
> このオプションは、Windows Server 2012 R2 では使用できません。 

## <a name="configure-automatic-exclusions"></a>自動除外を構成する

セキュリティとパフォーマンスを確保できるように、Windows Server 2016 や Windows Server 2019、またはWindows Server 2022 での Microsoft Defender ウイルス対策使用時に、インストールする役割と機能に基づいて特定の除外が自動的に追加されます。

詳細については、「[Windows Server 上の Microsoft Defender ウイルス対策で除外を構成する](configure-server-exclusions-microsoft-defender-antivirus.md)」を参照してください。

## <a name="passive-mode-and-windows-server"></a>パッシブ モードと Windows Server

Windows Server のプライマリウイルス対策ソリューションとして Microsoft 以外のウイルス対策製品を使用している場合は、Microsoft Defender ウイルス対策をパッシブ モードまたは無効モードに設定する必要があります。 Windows サーバー エンドポイントがMicrosoft Defender for Endpointにオンボードされている場合は、Microsoft Defender ウイルス対策をパッシブ モードに設定できます。 Microsoft Defender for Endpointを使用していない場合は、Microsoft Defender ウイルス対策を無効モードに設定します。 

> [!TIP]
> [他のセキュリティ製品との互換性Microsoft Defender ウイルス対策](microsoft-defender-antivirus-compatibility.md)参照してください。

次の表では、Microsoft Defender ウイルス対策をパッシブ モードに設定し、Microsoft Defender ウイルス対策を無効にし、Microsoft Defender ウイルス対策をアンインストールする方法について説明します。

| プロシージャ | 説明 |
|---|---|
| レジストリ キーを使用してMicrosoft Defender ウイルス対策をパッシブ モードに設定する | ForceDefenderPassiveMode レジストリ キーを次のように設定します。 <br/>- パス: `HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection` <br/>- 名前: `ForceDefenderPassiveMode` <br/>- 型: `REG_DWORD` <br/>- 値: `1` |
| PowerShell を使用して Microsoft Defender ウイルス対策ユーザー インターフェイスをオフにする | 管理者としてWindows PowerShellを開き、次の PowerShell コマンドレットを実行します。`Uninstall-WindowsFeature -Name Windows-Defender-GUI`
| PowerShell を使用してMicrosoft Defender ウイルス対策を無効にする | 次の PowerShell コマンドレットを使用します: `Set-MpPreference -DisableRealtimeMonitoring $true` |
| 役割と機能の削除ウィザードを使用して Microsoft Defender ウイルス対策を無効にする | 「[役割のインストールまたはアンインストール、役割サービス、または機能](/windows-server/administration/server-manager/install-or-uninstall-roles-role-services-or-features#remove-roles-role-services-and-features-by-using-the-remove-roles-and-features-wizard)」 を参照してから、**役割と機能の削除ウィザード** を使用します。 <br/><br/>ウィザードの **機能** ステップにアクセスし、**Windows Defender 機能** オプションを解除します。 <br/><br/> **[Windows Defender** 機能] セクションで単独で **Windows Defender** をオフにすると、**Windows Defenderの** インターフェイス オプション GUI を削除するように求められます。<br/><br/>Microsoft Defender ウイルス対策はユーザー インターフェイスなしでも通常どおり実行されますが、コア **Windows Defender** 機能を無効にした場合、ユーザー インターフェイスを有効にすることはできません。 |
| PowerShell を使用してMicrosoft Defender ウイルス対策をアンインストールする | 次の PowerShell コマンドレットを使用します: `Uninstall-WindowsFeature -Name Windows-Defender` |
| グループ ポリシーを使用してMicrosoft Defender ウイルス対策を無効にする | ローカル グループ ポリシー エディターで、**［管理テンプレート］** > **［Windows コンポーネント］** > **［Endpoint Protection］** > **［Endpoint Protection を無効にする］** に移動し、**［有効にする］** > **［OK］** を選択します。 |

### <a name="are-you-using-windows-server-2012-r2-or-windows-server-2016"></a>Windows Server 2012 R2 または Windows Server 2016 を使用していますか?

Windows サーバーがMicrosoft Defender for Endpointにオンボードされている場合は、Windows Server 2012 R2 とWindows Server 2016でパッシブ モードでMicrosoft Defender ウイルス対策を実行できるようになりました。 次の記事をご覧ください。

- [Microsoft Defender for Endpointをインストールするオプション](configure-server-endpoints.md#options-to-install-the-microsoft-defender-for-endpoint-packages)

- [Microsoft Defender ウイルス対策の他のセキュリティ製品との互換性](microsoft-defender-antivirus-compatibility.md)

## <a name="see-also"></a>関連項目

- [Windows の Microsoft Defender ウイルス対策](microsoft-defender-antivirus-windows.md)

