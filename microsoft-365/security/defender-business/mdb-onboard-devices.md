---
title: Microsoft Defender for Business へのオンボード デバイス (プレビュー)
description: Microsoft Defender for Business (プレビュー) のデバイスオンボーディング オプションについて説明します。
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: overview
ms.date: 02/16/2022
ms.prod: m365-security
ms.technology: mdb
localization_priority: Normal
ms.reviewer: inbadian, shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
- m365-initiative-defender-business
ms.openlocfilehash: 073478300e6b5a9d5a9fc10e634f6e3113897fb3
ms.sourcegitcommit: 007822d16e332522546e948f5c216327254a4d49
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/17/2022
ms.locfileid: "62879242"
---
# <a name="onboard-devices-to-microsoft-defender-for-business-preview"></a>Microsoft Defender for Business へのオンボード デバイス (プレビュー)

> [!IMPORTANT]
> Microsoft Defender for Business はプレビュー中で、ここでサインアップして要求する顧客と IT パートナーに徐[](https://aka.ms/mdb-preview)々にロールアウトされます。 今後数週間以内に最初の一連の顧客とパートナーをオンボードし、一般提供に至るプレビューを拡大します。 プレビューは最初の一連 [のシナリオで](mdb-tutorials.md#try-these-preview-scenarios)起動し、定期的に機能を追加します。
> 
> この記事の一部の情報は、製品リリース前に大幅に変更される可能性がある、事前リリース済みの製品/サービスに関連しています。 Microsoft は、ここに提供される情報について、明示または黙示を問わず一切の保証を行いません。 

Defender for Business のデバイス オンボーディング エクスペリエンスは、Microsoft Defender for Endpoint で使用されるのと同じデバイス オンボーディング プロセス上に構築されました。 次のビデオを見て、その動作を確認します。<br/><br/>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4bGqr]

Microsoft Defender for Business (プレビュー) では、組織のデバイスをオンボーディングするためのオプションがいくつか用意されています。 この記事では、オプションについて説明し、オンボーディングのしくみの概要について説明します。

> [!TIP]
> Defender for Endpoint でのデバイスオンボーディングの詳細については、「オンボード デバイス」を参照し、 [Microsoft Defender for Endpoint の機能を構成します](../defender-endpoint/onboard-configure.md)。

## <a name="what-to-do"></a>操作

1. オンボード デバイスのオプション [を参照してください](#device-onboarding-methods)。

2. 次のいずれかの方法を使用してデバイスをオンボードします。
    - [デバイスに登録されているWindowsデバイスの自動オンボーディングMicrosoft エンドポイント マネージャー](#automatic-onboarding-for-windows-devices-enrolled-in-microsoft-endpoint-manager)
    - [ローカル デバイス、macOS Windows Linux デバイス用のローカル スクリプト](#onboard-devices-using-a-local-script-in-defender-for-business)
    - [Microsoft エンドポイント マネージャー、タブレット、および電話の場合](#onboard-devices-using-microsoft-endpoint-manager)
    - [デバイスのグループ ポリシー Windowsポリシー](#onboard-windows-devices-using-group-policy)
    - [ここにリストされていない別のメソッド](#onboard-devices-using-a-method-not-listed-here)

3. [新しくオンボードされたデバイス](#run-a-detection-test)の検出テストをWindowsします。

4. [次の手順を参照してください](#next-steps)。 

この記事には、デバイスの [オフボードに関する情報も含まれています](#offboarding-a-device)。

## <a name="device-onboarding-methods"></a>デバイスオンボーディングの方法

次の表では、デバイスを Defender for Business にオンボードするために最も一般的に使用される方法について説明します。 

| オンボーディング方法  | 説明  |
|---------|---------|
| **自動オンボーディング**<br/>(*既にユーザーを使用しているお客様Microsoft エンドポイント マネージャー*) | 自動オンボーディングは、Defender for Business (プレビュー) と Microsoft エンドポイント マネージャー の間の接続をセットアップし、Windowsデバイスを Defender for Business (プレビュー) にオンボードします。 デバイスは、既にデバイスに登録されているエンドポイント マネージャー。<br/><br/>詳細については、「デバイスに登録されているデバイスの自動オンボーディングWindows[使用する」を参照Microsoft エンドポイント マネージャー](#automatic-onboarding-for-windows-devices-enrolled-in-microsoft-endpoint-manager)。 |
| **ローカル スクリプト**<br/>(*プレビュー中に推奨されます。一度にいくつかのデバイスをオンボーディングする場合に役立ちます*)  | コンピューターを Defender for Business (プレビュー) にオンボードするには、Windows、macOS、または Linux デバイスでダウンロードして実行するスクリプトを使用します。 このスクリプトは、デバイスに対する信頼Azure Active Directory設定し、デバイスを登録します。<br/><br/>このメソッドを使用するには、「 [Defender for Business のローカル スクリプトを使用したオンボード デバイス」を参照してください](#onboard-devices-using-a-local-script-in-defender-for-business)。 |
| **Microsoft Intune** または **Microsoft エンドポイント マネージャー**<br/>(*既にユーザーまたはユーザーを使用しているMicrosoft Intune利用可能エンドポイント マネージャー*) | [Microsoft Intune](/mem/intune/fundamentals/what-is-intune)モバイル [デバイスの管理は](/mem/intune/enrollment/device-enrollment)、デバイス管理の一部エンドポイント マネージャー。 Defender for Business (プレビュー) をエンドポイント マネージャー前に既にデバイスを使用していた場合は、引き続きデバイスのオンボードエンドポイント マネージャー管理する方法を選択できます。<br/><br/>このメソッドを使用するには、「デバイスを使用[したオンボード デバイスMicrosoft エンドポイント マネージャー](#onboard-devices-using-microsoft-endpoint-manager)。 |
| **グループ ポリシー** | 組織で既にグループ ポリシーを使用している場合は、GPO を作成し、Defender for Business (プレビュー) で組織のデバイスに適用できます。<br/><br/>この方法の詳細については、「グループ ポリシーを使用したオンボード [Windowsデバイス」を参照してください](#onboard-windows-devices-using-group-policy)。 | 

> [!IMPORTANT]
> 問題が発生してオンボーディング プロセスが失敗した場合は、「 [Microsoft Defender for Business のトラブルシューティング」を参照してください](mdb-troubleshooting.yml)。

## <a name="automatic-onboarding-for-windows-devices-enrolled-in-microsoft-endpoint-manager"></a>デバイスに登録されているWindowsデバイスの自動オンボーディングMicrosoft エンドポイント マネージャー

自動オンボーディング オプションは、デバイスWindows適用されます。 このオプションは、Defender for Business (プレビュー) を受け取る前に組織が Microsoft Intune で Microsoft エンドポイント マネージャー、Microsoft Intune、またはモバイル デバイス管理 (MDM) を既に使用し、Windows デバイスが既に登録されている場合に使用できます。エンドポイント マネージャー。 

Windowsデバイスが エンドポイント マネージャー に既に登録されている場合、Defender for Business は、Defender for Business のセットアップおよび構成中にそれらのデバイスを検出します。 すべてのデバイスまたは一部のデバイスに対して自動オンボーディングを使用Windowsされます。 

自動オンボーディング プロセスは、Defender for Business と エンドポイント マネージャー間の接続をセットアップし、デバイスを Defender for Business にオンボードします。 登録済みのすべてのデバイスを一度Windowsするか、オンボードするデバイスのセットWindows選択できます。

詳細については、「ウィザードを使用して [Microsoft Defender for Business (](mdb-use-wizard.md)プレビュー)をセットアップする」の手順 3 を参照してください。

## <a name="onboard-devices-using-a-local-script-in-defender-for-business"></a>Defender for Business のローカル スクリプトを使用したオンボード デバイス

ローカル スクリプトを使用して、Windows、macOS、Linux デバイスを Defender for Business にオンボードできます。 デバイスでオンボード スクリプトを実行すると、Azure Active Directory との信頼が作成され、Microsoft エンドポイント マネージャー にデバイスが登録され、デバイスが Defender for Business にオンボードされます。 このメソッドは、Defender for Business でデバイスをオンボーディングする場合や、一度にいくつかのデバイスをオンボーディングする場合に便利です。

1. ポータル () にMicrosoft 365 Defenderし[https://security.microsoft.com](https://security.microsoft.com)、サインインします。

2. ナビゲーション ウィンドウで、[設定 **Endpoints**] **を** > 選択し、[デバイスの管理] で [**オンボーディング]** **を選択します**。

3. オペレーティング システム (Windows 10 や **11** など) を選択し、[デバイスのオンボード] の [展開方法] セクションで、[ローカル スクリプト] **を選択します**。 

4. **[オンボーディング パッケージをダウンロードする]** を選択します。 オンボーディング パッケージをリムーバブル ドライブに保存することをお勧めします。

5. 次の記事のガイダンスに従います。

   - Windows: ローカル [スクリプトをWindowsデバイスのオンボード](../defender-endpoint/configure-endpoints-script.md#onboard-devices)
   - macOS デバイス: [macOS での Microsoft Defender for Endpoint の手動展開](../defender-endpoint/mac-install-manually.md#client-configuration)
   - Linux デバイス: [Linux で Microsoft Defender for Endpoint を手動で展開する](../defender-endpoint/linux-install-manually.md#client-configuration)

> [!IMPORTANT]
> 問題が発生してオンボーディング プロセスが失敗した場合は、「 [Microsoft Defender for Business (プレビュー) のトラブルシューティング」を参照してください](mdb-troubleshooting.yml)。

## <a name="onboard-devices-using-microsoft-endpoint-manager"></a>デバイスを使用したオンボード Microsoft エンドポイント マネージャー

Defender for Business (プレビュー) をMicrosoft Intune前に既にデバイスを使用していた場合は、引き続きデバイスMicrosoft Intuneを使用できます。 このエンドポイント マネージャー、コンピューター、タブレット、および電話をオンボードできます。 

「[デバイスの登録」を参照Microsoft Intune](/mem/intune/enrollment/device-enrollment)。

## <a name="onboard-windows-devices-using-group-policy"></a>グループ ポリシーを使用してデバイスをオンボードする

[グループ ポリシー](/previous-versions/windows/it-pro/windows-server-2012-r2-and-2012/hh831791(v=ws.11)) は、グループ ポリシーの設定とグループ ポリシーの基本設定を使用して、ユーザーとコンピューターの管理構成を指定できるインフラストラクチャです。 グループ ポリシー オブジェクト (GPO) は、グループ ポリシー コンテナーとグループ ポリシー テンプレートで構成される論理オブジェクトです。 

組織で既にグループ ポリシーを使用してデバイスを管理している場合は、グループ ポリシーを使用してデバイスを Defender for Business にオンボードできます。 グループ ポリシーを新しく使用する場合は、別の方法 (エンドポイント マネージャースクリプトなど) を使用することをお勧めします。 

「グループ [ポリシーをWindowsデバイスのオンボード」を参照してください](../defender-endpoint/configure-endpoints-gp.md)。

## <a name="onboard-devices-using-a-method-not-listed-here"></a>ここに記載されていないメソッドを使用してデバイスをオンボードする

この記事に記載されていない別の方法を使用してデバイスをオンボードする場合は、「オンボードと構成ツールのオプション」 [を参照してください](../defender-endpoint/onboard-configure.md#onboarding-and-configuration-tool-options)。

## <a name="run-a-detection-test"></a>検出テストを実行する

Windows デバイスを Defender for Business (プレビュー) にオンボードした後、Windows デバイスで検出テストを実行して、すべてが正しく動作するようにすることができます。

1. デバイスでWindowsフォルダーを作成します。 `C:\test-MDATP-test`

2. 管理者としてコマンド プロンプトを開きます。

3. [コマンド プロンプト] ウィンドウで、次の PowerShell コマンドを実行します。

   ```powershell
   powershell.exe -NoExit -ExecutionPolicy Bypass -WindowStyle Hidden $ErrorActionPreference = 'silentlycontinue';(New-Object System.Net.WebClient).DownloadFile('http://127.0.0.1/1.exe', 'C:\\test-MDATP-test\\invoice.exe');Start-Process 'C:\\test-MDATP-test\\invoice.exe'
   ```

コマンドを実行すると、[コマンド プロンプト] ウィンドウが自動的に閉じます。 成功した場合、検出テストは完了としてマークされ、新しくオンボードされたデバイスの Microsoft 365 Defender ポータル ([https://security.microsoft.com](https://security.microsoft.com)) に約 10 分で新しいアラートが表示されます。

## <a name="gradual-device-onboarding"></a>段階的なデバイスオンボーディング

組織のデバイスを段階的にオンボードする場合は、次の手順を実行します。

1. オンボードするデバイスのセットを識別します。

2. ポータル () にMicrosoft 365 Defenderし[https://security.microsoft.com](https://security.microsoft.com)、サインインします。

3. ナビゲーション ウィンドウで、[設定 **Endpoints**] **を** > 選択し、[デバイスの管理] で [**オンボーディング]** **を選択します**。

4. オペレーティング システム (Windows 10 **11 など) を選択** し、オンボーディング方法 (ローカル スクリプトなど) **を選択します**。 選択した方法のガイダンスに従います。

5. オンボードするデバイスのセットごとにこのプロセスを繰り返します。 

> [!TIP]
> デバイスをオンボードする度に同じオンボーディング パッケージを使用する必要はない。 たとえば、ローカル スクリプトを使用して一部のデバイスをオンボードし、後で別の方法を選択して、より多くのデバイスをオンボードできます。

## <a name="offboarding-a-device"></a>デバイスのオフボード

デバイスをオフボードする場合は、次の手順を実行します。

1. ポータル () にMicrosoft 365 Defenderサインイン[https://security.microsoft.com](https://security.microsoft.com)します。

2. ナビゲーション ウィンドウで、[エンドポイント **] を設定** し、[エンドポイント] **を選択します**。

3. [ **デバイスの管理] で**、[ **オフボード] を選択します**。

4. オペレーティング システム (Windows 10 および **11** など) を選択し、[デバイスのオフボード] の [展開方法] セクションで、[ローカル  スクリプト] を **選択します**。 

5. 確認画面で情報を確認し、[ダウンロード] を選択 **して** 続行します。

6. [オフ **ボード パッケージのダウンロード] を選択します**。 オフボード パッケージをリムーバブル ドライブに保存することをお勧めします。

7. オフボードする各デバイスでスクリプトを実行します。 

   このタスクに関するヘルプが必要ですか? 以下のリソースを参照してください。   

   - Windows: [ローカル スクリプトを使用Windowsオフボード デバイス](../defender-endpoint/configure-endpoints-script.md#offboard-devices-using-a-local-script)
   - macOS デバイス: [macOS でのアンインストール](../defender-endpoint/mac-resources.md#uninstalling)
   - Linux デバイス: [Linux でのアンインストール](../defender-endpoint/linux-resources.md#uninstall)

> [!IMPORTANT]
> デバイスをオフボードすると、デバイスは Defender for Business (プレビュー) へのデータの送信を停止します。 ただし、オフボード前に受信したデータは、最大 6 か月間保持されます。

## <a name="next-steps"></a>次の手順

次の手順に進みます。

- [手順 5: Microsoft Defender for Business でセキュリティ設定とポリシーを構成する (プレビュー)](mdb-configure-security-settings.md)

- [Microsoft Defender for Business の使用を開始する (プレビュー)](mdb-get-started.md) 