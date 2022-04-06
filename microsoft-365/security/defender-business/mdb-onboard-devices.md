---
title: デバイスをオンボードMicrosoft Defender for Business
description: デバイスオンボーディングオプションの詳細については、「Microsoft Defender for Business
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: overview
ms.date: 04/01/2022
ms.prod: m365-security
ms.technology: mdb
ms.localizationpriority: medium
ms.reviewer: inbadian, shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
- m365-initiative-defender-business
ms.openlocfilehash: 78a8eaa5a9472a32c9615dfb7c7f5b08afe548ff
ms.sourcegitcommit: adea59259a5900cad5de29ddf46d1ca9e9e1c82f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/04/2022
ms.locfileid: "64634737"
---
# <a name="onboard-devices-to-microsoft-defender-for-business"></a>デバイスをオンボードMicrosoft Defender for Business

> [!IMPORTANT]
> Microsoft Defender for Business 2022 年 3 月 1 [日](../../business-premium/index.md)からMicrosoft 365 Business Premium顧客に展開しています。 スタンドアロン サブスクリプションとしての Defender for Business はプレビュー中で、ここでサインアップして要求する顧客と IT パートナーに徐 [々にロールアウト](https://aka.ms/mdb-preview) されます。 プレビューには最初 [の一連のシナリオが含まれています](mdb-tutorials.md#try-these-preview-scenarios)。定期的に機能を追加します。
> 
> この記事の一部の情報は、製品リリース前に大幅に変更される可能性がある、事前リリース済みの製品/サービスに関連しています。 Microsoft は、ここに提供される情報について、明示または黙示を問わず一切の保証を行いません。 

このMicrosoft Defender for Business、会社のデバイスをオンボーディングするためのオプションがいくつかあります。 この記事では、オプションについて説明し、オンボーディングのしくみの概要について説明します。

>
> **少し時間ありますか?**
> お問い合<a href="https://microsoft.qualtrics.com/jfe/form/SV_0JPjTPHGEWTQr4y" target="_blank">わせに関する短いMicrosoft Defender for Business</a>。 ご意見をお寄せください。
>

## <a name="what-to-do"></a>操作

1. [オンボーディング デバイスのオプションを確認し](#device-onboarding-methods)、方法を選択します。 

   - [デバイスに既に登録されているデバイスWindows自動オンボーディングを使用Microsoft エンドポイント マネージャー](#automatic-onboarding-for-windows-devices-enrolled-in-microsoft-endpoint-manager)
   - [ローカル スクリプトを使用して、Windowsまたは macOS デバイスをオンボードする](#local-script-in-defender-for-business)
   - [モバイル Microsoft エンドポイント マネージャー、macOS、Windowsデバイスのオンボードに使用する](#microsoft-endpoint-manager)

2. [新しくオンボードされたデバイス](#run-a-detection-test)で検出テストをWindowsします。

3. [次の手順を参照してください](#next-steps)。 

この記事には、デバイスの [オフボードに関する情報も含まれています](#offboarding-a-device)。

## <a name="device-onboarding-methods"></a>デバイスオンボーディングの方法

Defender for Business では、既に Microsoft エンドポイント マネージャー を使用している場合でも、簡単なオンボーディング エクスペリエンスが必要な場合でも、デバイスをオンボーディングする方法がいくつか用意されています。 デバイスを Defender for Business にオンボードするために最も一般的に使用される方法は次のとおりです。

- **デバイスに既に** Windowsされているデバイスの自動オンボーディングMicrosoft エンドポイント マネージャー。 自動オンボーディングは、Defender for Business と Microsoft エンドポイント マネージャー間の接続をセットアップし、Windows Defender for Business にデバイスをオンボードします。 このオプションを使用するには、デバイスが既にデバイスに登録されている必要エンドポイント マネージャー。 詳細については、「自動オンボーディング [」を参照してください](#automatic-onboarding-for-windows-devices-enrolled-in-microsoft-endpoint-manager)。

- **ローカル スクリプトを使用** して、Windows macOS デバイスを Defender for Business に手動でオンボードします。 ローカル スクリプトを使用すると、一度に最大 10 台のデバイスをオンボードできます。 詳細については、「Defender [for Business のローカル スクリプト」を参照してください](#local-script-in-defender-for-business)。

- **Microsoft Intune**、**macOS Microsoft エンドポイント マネージャー** モバイル デバイスWindowsオンボーディングを行います。 デバイスをデバイスに登録エンドポイント マネージャー、デバイスを Defender for Business にオンボードできます。 [Microsoft 365 Business Premium](../../business-premium/index.md)ユーザー[は既に](/mem/intune/fundamentals/what-is-intune)Microsoft Intuneし、Microsoft Intuneモバイル デバイス管理は現在、エンドポイント マネージャーの一部エンドポイント マネージャー[](/mem/intune/enrollment/device-enrollment)。 このメソッドを使用するには、「Microsoft エンドポイント マネージャー」 [を参照してください](#microsoft-endpoint-manager)。

> [!IMPORTANT]
> 問題が発生し、オンボーディング プロセスが失敗した場合は、「トラブルシューティング[Microsoft Defender for Business参照してください](mdb-troubleshooting.yml)。

## <a name="automatic-onboarding-for-windows-devices-enrolled-in-microsoft-endpoint-manager"></a>デバイスに登録Windowsデバイスの自動オンボーディングMicrosoft エンドポイント マネージャー

自動オンボーディング オプションは、デバイスWindows適用されます。 自動オンボーディングは、次の条件が満たされている場合に使用できます。

- Defender for Business をMicrosoft エンドポイント マネージャーする前Microsoft エンドポイント マネージャー、Microsoft Intune、またはモバイル デバイス管理 (MDM) をMicrosoft Intuneしている会社

- 既に、Windowsに登録されているデバイスエンドポイント マネージャー

Windowsデバイスが エンドポイント マネージャー に既に登録されている場合、Defender for Business は、Defender for Business のセットアップおよび構成中にそれらのデバイスを検出します。 すべてのデバイスまたは一部のデバイスに対して自動オンボーディングを使用Windowsされます。 すべてのデバイスを一度Windowsしたり、最初に特定のデバイスを選択したり、後でデバイスを追加したりできます。

> [!TIP]
> [すべてのデバイスが登録されている] オプションを選択することをお勧めします。 この方法で、Windowsデバイスが後で登録エンドポイント マネージャー、Defender for Business に自動的にオンボードされます。 また、エンドポイント マネージャー でセキュリティ ポリシーと設定を管理している場合は、Microsoft 365 Defender ポータルに切り替えてデバイス、ポリシー、設定を管理することをお勧めします。 詳細については、「セキュリティ ポリシーと [デバイスを管理する場所を選択する」を参照してください](mdb-configure-security-settings.md#choose-where-to-manage-security-policies-and-devices)。

自動オンボーディングの詳細については、「ウィザードを使用して自動オンボーディングをセットアップする」の手順 2 [を参照](mdb-use-wizard.md)Microsoft Defender for Business。

## <a name="local-script-in-defender-for-business"></a>Defender for Business のローカル スクリプト

ローカル スクリプトを使用して、ローカル デバイスと Mac Windowsオンボードできます。 デバイスでオンボード スクリプトを実行すると、Azure Active Directory との信頼が作成されます (その信頼が存在しない場合)、Microsoft エンドポイント マネージャー にデバイスを登録し (まだ登録されていない場合)、デバイスを Defender for Business にオンボードします。 このメソッドは、Defender for Business のデバイスをオンボーディングする場合に便利です。 最大 10 台のデバイスを一度にオンボードできます。

1. ポータル () にMicrosoft 365 Defenderし[https://security.microsoft.com](https://security.microsoft.com)、サインインします。

2. ナビゲーション ウィンドウで、[設定 **Endpoints**] **を** > 選択し、[デバイスの管理] で [**オンボーディング]** **を選択します**。

3. オペレーティング システム (Windows 10 **11** や **macOS** など) を選択し、[展開方法] セクションで [ローカル スクリプト]  **を選択します**。 

4. **[オンボーディング パッケージをダウンロードする]** を選択します。 オンボーディング パッケージをリムーバブル ドライブに保存することをお勧めします。 (**macOS** を選択した場合は、[インストール  パッケージをダウンロードしてリムーバブル デバイスに保存する] も選択します)。

5. 次の表のガイダンスに従います。

   | オペレーティング システム | プロシージャ |
   |---|---|
   | Windows | 1. デバイスWindows、構成パッケージの内容をデスクトップ フォルダーなどの場所に展開します。 という名前のファイルが必要です `WindowsDefenderATPLocalOnboardingScript.cmd`。 <br/><br/>2. 管理者としてコマンド プロンプトを開きます。<br/><br/>3. スクリプト ファイルの場所を入力します。 たとえば、ファイルをデスクトップ フォルダーにコピーした場合は、「: `%userprofile%\Desktop\WindowsDefenderATPLocalOnboardingScript.cmd`」と入力し、Enter キーを押します (または **[OK] を選択します**)。<br/><br/>4. スクリプトの実行後、[検出テストの [実行] に進みます](#run-a-detection-test)。 |
   | macOS | 1. Mac コンピューターで、インストール パッケージをローカル ディレクトリ `wdav.pkg` に保存します。 <br/><br/>2. オンボーディング パッケージをインストール パッケージ `WindowsDefenderATPOnboardingPackage.zip` に使用したのと同じディレクトリに保存します。 <br/><br/>3. Finder を使用して保存した `wdav.pkg` 場所に移動し、開きます。<br/><br/>4. [ **続行] を** 選択し、ライセンス条項に同意し、メッセージが表示されたらパスワードを入力します。<br/><br/>5. Microsoft のドライバーのインストールを許可するように求めるメッセージが表示されます ("System Extension Blocked" または "Installation is on hold"、または両方)。 ドライバーのインストールを許可する必要があります。 インストールを許可するには、[Open **Security Preferences**] または [**Open System PreferencesSecurity** >  &**プライバシー**] を選択し、[許可] を選択 **します**。<br/><br/>6. Bash で次の Python コマンドを使用してオンボーディング パッケージを実行します。 `/usr/bin/python MicrosoftDefenderATPOnboardingMacOs.py` <br/><br/>7. デバイスが会社に関連付けられているか確認するには、Bash で次の Python コマンドを使用します。 `mdatp health --field org_id`<br/><br/>8. macOS 10.15 (Catalina) 以降を使用している場合は、デバイスを保護するために Defender for Business の同意を付与します。 「**System PreferencesSecurity** >  **&** **PrivacyFull** >  >  **Disk Access」に移動します**。  ロック アイコンを選択して変更を加えます (ダイアログ ボックスの下部) をクリックし、Microsoft Defender for Business (または Defender for Endpoint) を選択します(表示されている場合)。 <br/><br/>9. デバイスがオンボードされているのを確認するには、Bash で次のコマンドを使用します。 `mdatp health --field real_time_protection_enabled`    |

## <a name="microsoft-endpoint-manager"></a>Microsoft エンドポイント マネージャー

Defender for Business を使用する前に エンドポイント マネージャー (Microsoft Intune とモバイル デバイス管理 を含む) を既に使用していた場合は、引き続き エンドポイント マネージャー を使用して会社のデバイスをオンボードできます。 このエンドポイント マネージャー、iOS デバイスや Android デバイスを含むコンピューター、タブレット、電話をオンボードできます。

「[デバイスの登録」を参照Microsoft Intune](/mem/intune/enrollment/device-enrollment)。

## <a name="run-a-detection-test"></a>検出テストの実行

Defender for Business に Windowsデバイスをオンボードした後、Windows デバイスで検出テストを実行して、すべてが正しく動作するようにすることができます。

1. デバイスでWindowsフォルダーを作成します。 `C:\test-MDATP-test`

2. 管理者としてコマンド プロンプトを開きます。

3. [コマンド プロンプト] ウィンドウで、次の PowerShell コマンドを実行します。

   ```powershell
   powershell.exe -NoExit -ExecutionPolicy Bypass -WindowStyle Hidden $ErrorActionPreference = 'silentlycontinue';(New-Object System.Net.WebClient).DownloadFile('http://127.0.0.1/1.exe', 'C:\\test-MDATP-test\\invoice.exe');Start-Process 'C:\\test-MDATP-test\\invoice.exe'
   ```

コマンドを実行すると、[コマンド プロンプト] ウィンドウが自動的に閉じます。 成功した場合、検出テストは完了としてマークされ、新しくオンボードされたデバイスの新しいアラートが Microsoft 365 Defender ポータル ([https://security.microsoft.com](https://security.microsoft.com)) に約 10 分で表示されます。

## <a name="gradual-device-onboarding"></a>段階的なデバイスオンボーディング

会社のデバイスを段階的にオンボードできます。 *この段階的なデバイスオンボーディングを呼び出します*。 

1. オンボードするデバイスのセットを識別します。

2. ポータル () にMicrosoft 365 Defenderし[https://security.microsoft.com](https://security.microsoft.com)、サインインします。

3. ナビゲーション ウィンドウで、[設定 **Endpoints**] **を** > 選択し、[デバイスの管理] で [**オンボーディング]** **を選択します**。

4. オペレーティング システム (Windows 10 **11 など) を** 選択し、オンボーディング方法 (ローカル スクリプトなど) **を選択します**。 選択した方法のガイダンスに従います。

5. オンボードするデバイスのセットごとにこのプロセスを繰り返します。 

> [!TIP]
> デバイスをオンボードする度に同じオンボーディング パッケージを使用する必要はない。 たとえば、ローカル スクリプトを使用して一部のデバイスをオンボードし、後で別の方法を選択して、より多くのデバイスをオンボードできます。

## <a name="offboarding-a-device"></a>デバイスのオフボード

デバイスをオフボードする場合は、次のいずれかの手順を使用します。

| オペレーティング システム | プロシージャ |
|---|---|
| Windows | 1. ポータル () のMicrosoft 365 Defenderサインイン[https://security.microsoft.com](https://security.microsoft.com)します。<br/><br/>2. ナビゲーション ウィンドウで、[エンドポイント] を **設定し、[** エンドポイント] **を選択します**。<br/><br/>3. [デバイス **の管理] で、[****オフボード] を選択します**。<br/><br/>4. オペレーティング システム (**Windows 10 や 11** など) を選択し、[デバイスのオフボード] の [展開方法] セクションで、[ローカル スクリプト] を **選択します**。 <br/><br/>5. 確認画面で情報を確認し、[ダウンロード] を選択 **して続行します** 。<br/><br/>6. [オフ **ボード パッケージのダウンロード] を選択します**。 オフボード パッケージをリムーバブル ドライブに保存することをお勧めします。<br/><br/>7. オフボードする各デバイスでスクリプトを実行します。| 
| macOS | 1. **FinderApplications** >  に移動します。 <br/><br/>2. [ごみ箱] を右Microsoft Defender for Businessし、[ごみ箱に移動] **を選択します**。 <br/><br/>--- または --- <br/><br/> 次のコマンドを使用します。 `sudo '/Library/Application Support/Microsoft/Defender/uninstall/uninstall'`|

> [!IMPORTANT]
> デバイスをオフボードすると、デバイスは Defender for Business へのデータの送信を停止します。 ただし、オフボード前に受信したデータは、最大 6 か月間保持されます。

## <a name="next-steps"></a>次の手順

次の手順に進みます。

- [手順 5: セキュリティ設定とポリシーを構成する方法Microsoft Defender for Business](mdb-configure-security-settings.md)

- [概要を使用Microsoft Defender for Business](mdb-get-started.md) 
